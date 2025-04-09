# 5.5 RECAP AND PREVIEW

In this chapter, we reviewed the univariate normal probability distribution and took a look at the historical returns on the. $\mathrm{S\&RP}~500$ to see how well the distribution fits the data. We. also examined the bivariate normal probability distribution, which can apply when there are two random variables.

In Chapter 6, we take a brief review of the basic concepts in valuing risky assets and derivatives.

# APPENDIX 5A

# An Excel Routine for the Bivariate Normal Probability

The two variables are identified as *a* and *b*, and the correlation is *rho*. Enter them into three cells, which for the sake of illustration will be A1, B1, and C1. Then, in a separate cell, type the function `=bivar(A1,B1,C1)`. The code, which is presented next, should be entered using the Visual Basic for Applications feature of Excel. Choose the Developer tab. Then choose Visual Basic. Then Insert, then Module. You will then have a blank space on which to enter the following code.

**VB Code:**

```vba
Sub biv1(az, bz, rhoz, bprob)
'Subroutine used to compute bivariate normal probability
Dim bpl, bp2, bp3, bp4, prob
bp1 = phiz(az, bz, rhoz)
bp2 = Application.NormsDist(az) - phiz(az, -bz, -rhoz)
bp3 = Application.NormsDist(bz) - phiz(-az, bz, -rhoz)
bp4 = Application.NormsDist(az) + Application.NormsDist(bz) - 1 + phiz(-az, -bz, rhoz)
bprob = 0
11 If rhoz = 0 Then
    bprob = Application.NormsDist(az) * Application.NormsDist(bz)
Else
    GoTo 12
End If
GoTo 55
12 If az <= 0 And bz <= 0 And rhoz <= 0 Then
    bprob = bp1
Else
    GoTo 13
End If
GoTo 55
13 If az <= 0 And bz >= 0 And rhoz >= 0 Then
    bprob = bp2
Else
    GoTo 14
End If
GoTo 55
14 If az >= 0 And bz <= 0 And rhoz >= 0 Then
    bprob = bp3
Else
    GoTo 15
End If
GoTo 55
15 If az >= 0 And bz >= 0 And rhoz <= 0 Then
    bprob = bp4
Else
    GoTo 16
End If
16
GoTo 55
55 End Sub

Sub biv2(az, bz, rhoz, bprob)
'Subroutine used to compute bivariate normal probability
Dim signa, signb, rhoab, rhoba, Delta, probab, probba
If az >= 0 Then
    signa = 1
Else
    signa = -1
End If
If bz >= 0 Then
    signb = 1
Else
    signb = -1
End If
rhoab = (rhoz * az - bz) * signa / Sqr(az ^ 2 - 2 * rhoz * az * bz + bz ^ 2)
rhoba = (rhoz * bz - az) * signb / Sqr(az ^ 2 - 2 * rhoz * az * bz + bz ^ 2)
Delta = ((1 - signa) * signb) / 4
Call biv1(az, 0, rhoab, probab)
Call biv1(bz, 0, rhoba, probba)
bprob = probab + probba - Delta
End Sub

Function bivar(az, bz, rhoz)
'Function to compute bivariate normal probability
Dim bprob
If az * bz * rhoz > 0 Then
    GoTo 20
End If
Call biv1(az, bz, rhoz, bprob)
GoTo 56
20
Call biv2(az, bz, rhoz, bprob)
56 bivar = bprob
End Function

Function phiz(aa, bb, rhoo)
'sub-function to compute bivariate normal probability
Dim al, bl, fsum, i, j, f, phizz
Static w(5), x(5)
w(1) = 0.24840615: x(1) = 0.10024215
w(2) = 0.39233107: x(2) = 0.48281397
w(3) = 0.21141819: x(3) = 1.0609498
w(4) = 0.03324666: x(4) = 1.7797294
w(5) = 0.00082485334: x(5) = 2.6697604
al = aa / Sqr(2 * (1 - rhoo ^ 2))
bl = bb / Sqr(2 * (1 - rhoo ^ 2))
fsum = 0
For i = 1 To 5
    For j = 1 To 5
        f = Exp(al * (2 * x(i) - al) + bl * (2 * x(j) - bl) + 2 * rhoo * (x(i) - al) * (x(j) - bl))
        fsum = fsum + w(i) * w(j) * f
    Next j
Next i
phizz = fsum / 2 / 3.14159265358979
phiz = phizz
End Function
```


![](images/dcaaf5bcb77a70afb3ae251b6a767389bd7003f13fdfb0d678affea74648e554.jpg)

# Basic Concepts in Valuing Risky Assets and Derivativesd

some basic principles that comprise the foundation for valuing assets, after which we. will extend those principles to valuing financial derivatives, especially options. A more. rigorous foundation for these results is found in most classic works on the theory of finance, such as Fama (1976), Fama and Miller (1972), Huang and Litzenberger (1988), Ingersoll (1987), and Jarrow (1988).
