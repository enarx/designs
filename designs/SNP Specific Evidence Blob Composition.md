# SNP Specific Evidence Blob Composition

###### tags: `Design`
| Author | Period | State |
| -------- | -------- | -------- |
| Nathaniel McCallum<br>Dmitri Pal | January 2023 | :red_circle: **Draft** |


```mermaid
graph BT
    Steward(Steward)
    subgraph Shim[Shim]
            ShimEvVCEK(VCEK)
            ShimEvCRLs(CRLs)
            ShimEvReport(Report)
            ShimEvidence(ASN1 Combined Evidence)
    end

    subgraph Ex[Exec]
        ExEvidence(ASN1 Evidence Blob<br><i>no parsing</i>)
    end

    subgraph Host
        HostVCEK(VCEK)
        HostCRLs(CRLs)
    end    
    subgraph Firmware
        FirmwareReport[Report]
    end    
    FirmwareReport --> ShimEvReport
    HostVCEK --> ShimEvVCEK
    HostCRLs --> ShimEvCRLs
    ExEvidence --> Steward
    ShimEvVCEK --> ShimEvidence
    ShimEvCRLs --> ShimEvidence
    ShimEvReport --> ShimEvidence
    ShimEvidence --> ExEvidence

```