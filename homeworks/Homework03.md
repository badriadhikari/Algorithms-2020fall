# Homework 3

## Read sections 15.2, 15.3, and 15.4 from CLRS
Please read this with the goal of using the knowledge to do the homework below.

## Watch the recorded lectures
- [When is dynamic programming applicable and how to apply it?](https://www.youtube.com/watch?v=G4bsu48KVvs)
- [Example applications of dynamic programming](https://www.youtube.com/watch?v=Y9hfE7Y2hi4)
- [Solving the Matrix-chain multiplication problem using dynamic programming](https://youtu.be/qiB8GmqUJOU)
- [The Alignment Game and the Longest Common Subsequence Problem](https://youtu.be/W-WtMvNdEcM)
- [What is the longest common subsequence problem?](https://youtu.be/k1OmILy0Jmo)
- [Recursive solution for the longest common subsequence problem](https://youtu.be/btmBOSTLyzA)
- [Optimal-substructure property of the longest common subsequence problem](https://youtu.be/gclucr32fHg)
- [Dynamic programming for solving the longest common subsequence problem](https://youtu.be/FG17mqIwGDs)

## Question 1
Discuss a problem where dynamic programming is not applicable and explain why dynamic programming is not applicable to the problem.

## Question 2
With the help of an example, discuss the steps involved in developing a dynamic programming algorithm to solve a problem.

## Question 3 (programming)
For the problem of calculating n<sup>th</sup> Fibonacci number - (a) propose a recursive solution (implementation), (b) a dynamic programming solution using the top-down approach, and (c) a dynamic programming solution using the bottom-up approach. Test the running time of the three implemetations with large values of n and discuss your running time. You can use (not required) the libraries such as [timeit](https://docs.python.org/3/library/timeit.html) to check your running times.

## Question 4
What is the matrix chain multiplication problem? Discuss how dynamic programming can be applied to solve it.

## Question 5 (programming)
The "non structural protein 2" (`nsp2`) protein is found to be linked to the mechanism of Coronavirus ([read more](https://onlinelibrary.wiley.com/doi/10.1002/jmv.25719)). Below is the sequence of this protein (first two lines, ignoring the line starting with a hash). In addition to the sequence of this protein, below are the sequences of two other similar (homologous) proteins (see [nsp2.hhba3m.txt](./nsp2.hhba3m.txt) for the alignment). Implement a dynamic programming solution to calculate the longest common subsequence (LCS) between - (a) `nsp2` and `A0A1B3Q5V8` and (b) `nsp2` and `Q9YMB7`. These are two problems that can be solved using the same implementation/code. Lower-case letters in the sequences, if there are any, must be skipped totally. You should print not just the length of the LCS but also the actual LCS.

```
# The lines starting with > are header lines that are the names of the sequence
# Lower-case letters in the sequences must be skipped totally.
>nsp2
AYTRYVDNNFCGPDGYPLECIKDLLARAGKASCTLSEQLDFIDTKRGVYCCREHEHEIAWYTERSEKSYELQTPFEIKLAKKFDTFNGECPNFVFPLNSIIKTIQPRVEKKKLDGFMGRIRSVYPVASPNECNQMCLSTLMKCDHCGETSWQTGDFVKATCEFCGTENLTKEGATTCGYLPQNAVVKIYCPACHNSEVGPEHSLAEYHNESGLKTILRKGGRTIAFGGCVFSYVGCHNKCAYWVPRASANIGCNHTGVVGEGSEGLNDNLLEILQKEKVNINIVGDFKLNEEIAIILASFSASTSAFVETVKGLDYKAFKQIVESCGNFKVTKGKAKKGAWNIGEQKSILSPLYAFASEAARVVRSIFSRTLETAQNSVRVLQKAAITILDGISQYSLRLIDAMMFTSDLATNNLVVMAYITGGVVQLTSQWLTNIFGTVYEKLKPVLDWLEEKFKEGVEFLRDGWEIVKFISTCACEIVGGQIVTCAKEIKESVQTFFKLVNKFLALCADSIIIGGAKLKALNLGETFVTHSKGLYRKCVKSREETGLLMPLKAPKEIIFLEGETLPTEVLTEEVVLKTGDLQPLEQPTSEAVEAPLVGTPVCINGLMLLEIKDTEKYCALAPNMMVTNNTFTLKGG
>A0A1B3Q5V8
FLTDQYGFDADGVLAAPIKEVLGDKGAGMSlveltkflgkyRTADGYELPSGIVKVAVKVVRKNLPVSKQSIFTVLGVTERVVDGFYYPYSTNSVVSYTKPRAGATVGNTVQSVMLSVYGTEAYNPVTPVVRLRCSSCDFYGWVPVKDLGCVTCSCAAVHQitsSCIDAESAGLIKQGAVMLVDRSPSMRVVPGNRlYVAFGGAIWSPIGKVNGVQVWVPRAYSCVAGDHSGAVGSGDVnTINKEIMSLIIDGVRIDDEVLEQPSCGVLIANLEDPSAAPRVHTVDSLRQLCVDNNvmlgDTplpKDEFHPgivGLSYHFYRACWYGVLTAKSFGAFKELLQSEEVRLSHFCANIRRCLDRALNWARTTGnvsllssSLVLKALAENLLDSVKNTPFLVGDLVKPVLDWIVEKMVLARDSVVSCAEAVLSLFNMQFTFAKGKFTFLKEKLNKSCVALRELLTVIVNKFATTVKWAGCKIDGFYNGDYHFFSAKGVLTEVQVCAKTLGAMLtPRQQRMEVEVLDGKYdAPVAITVPELEELNGTLEEVFGFDDLTLVRGSLVALASKVFVRTDDGLLFRYVKSGGVFLKAFRLRGG
>Q9YMB7
YVDQYMCGADGKPVieGDFKDYFGDEDIIEFEGEEYHCAWTTVRDEKPLNQQTLFTIQEIQYNLDIPHKLPNCATRHVAPPVKKNSKIVLsedYKKLYDIFGSPFMGNGDCLSKCFDTLHFIAATlRCPCGSESSGVGDWTGFKTACCglSGKVKGVTLGDIKPGDAVvtsMSAGKgVKFFANCVLQYAGDVEGVSIWKVIKTFTVDETVCTPGFEGELNDFIKPESKSLVACSVKRAFITGDIDDAVHDCIITGKLDLSTNLFGNVGlLFKKTPWFvQKCGALFVDAWKVVEELCGSLTLTYKQIYEVVASLCTSAFTIVNYkpTFVVPDNRVKDLVDKCVKVLVKAFDVFTQIITIAGIEAKCFVLGAKYLLFNNALVKLVSVKILGKkQKgLECAFfatsLVGATVNVTPKRTETATISLNKVDDVVAPGEGYIVIVGDMAFYKSGEYYFMMSSPNFVLTNNVFK
```

## Question 6 (programming)
Implement a dynamic programming solution to calculate the longest common subsequence (LCS) of `⟨1,0,0,1,0,1,0,1⟩` and `⟨0,1,0,1,1,0,1,1,0⟩` (CLRS: 15.4-1). You can reuse the code that you developed for solving Q#5.

# Optional

## Question 7 
Let X = ⟨x 1 , x 2 , …, x m ⟩ and Y = ⟨y 1 , y 2 , …, y n ⟩ be sequences, and let Z = ⟨z 1 , z 2 , …, z k ⟩ be any LCS of X
and Y. Describe, mathematically, how the LCS problem exhibits the optimal substructure property. (Hint:
consider three cases).

## Question 8

Someone has the following as the top-down dynamic programming implementation for calculating nth Fibonacci number. Is this correct? Discuss.
```python
def fib_top_down(n):
    result = [0] * (n + 1)
    if n == 0:
        return 0 
    elif n == 1 or n == 2:
        return 1
    if result[n] != 0:
        return result[n]
    result[n] = fib_top_down(n-1) + fib_top_down(n-2)
    return result[n]
```

