[![](https://mermaid.ink/img/pako:eNqVlV1v2jAUhv-K5d1S2iSEQjRVKqCplejKoFWlQS9MfALRTBI5pi0t_e87dkISQmm3XES2n_d82OfEeaN-zIF6dCFZsiTD8Swi-KTrebZwHSmQEahsWT_9wc_p5etagh59n8vTi36MokiRAYjwCeTmMRNDxLNBzWVmPIZFGEelWx5K8BUukbteuXo57OXBhjHjpMcEi3yQj6WiHJUBkoRMQD6FPqQlNu5G19YUX7itVGlPxHo8UNj7CruiKLZ0JPKAKUaGbANy3-vk13A0xRcZyXDFihOq4LHBY0hE6DNzqmPADd9Goi7uDW97056I52SiYskW8B_5TRRToU_ygtWSeLic5vwB5voQ010eviI_pLHhHwU7Vui-CDFKpQQ9GT-nIKf3-NpNKg5HQp-cNR2EaYLDvdpkzC6YfcCcgjkfN2AekJycXGyv7u5Gk63ec8ZwYNZ15ftMiHSrWy9jONDMNM_Bil2NoBXGzYMMFWxN2QtiHyWZja63AeOaSR3kGaMHctI03DSN_nYOZYX7-0TgF3Q6iJ8jPdiaPqpF-kSTHyHOjbLP_CVuA2-AKs4LaBQTFPC1gNMrYFLNganKkebV_Feh87XwMIEb4CEj5V6KXKvBvxA5n4vyflcbAUV3BaEQ3jewAjcIqnyXWsaDACywDrn9BXeOct3BGeMt4JxVmWmCDPo-1BIz1T8GTZftQgaOz2twvIMdfr4f07RKfhjnvBW4VYgnuEvWAj-waAP_PyGnnpJraNAVyBXTU_qmrWZULWEFM-rhkDP5Z0Zn0TvaJCz6HcernZmM14sl9QImUpytE84UDEKGl1EpwTsBZD9eR4p6Hde4oN4bfaGe6zSdVrfdtWync95xXKdBN9SzXKvZcc7cTrvdabecduu9QV9NzLNm125bZ13XRQOnZaMe-wSv5Jvsh2r-q-9_AaR1L4g?type=png)](https://mermaid.live/edit#pako:eNqVlV1v2jAUhv-K5d1S2iSEQjRVKqCplejKoFWlQS9MfALRTBI5pi0t_e87dkISQmm3XES2n_d82OfEeaN-zIF6dCFZsiTD8Swi-KTrebZwHSmQEahsWT_9wc_p5etagh59n8vTi36MokiRAYjwCeTmMRNDxLNBzWVmPIZFGEelWx5K8BUukbteuXo57OXBhjHjpMcEi3yQj6WiHJUBkoRMQD6FPqQlNu5G19YUX7itVGlPxHo8UNj7CruiKLZ0JPKAKUaGbANy3-vk13A0xRcZyXDFihOq4LHBY0hE6DNzqmPADd9Goi7uDW97056I52SiYskW8B_5TRRToU_ygtWSeLic5vwB5voQ010eviI_pLHhHwU7Vui-CDFKpQQ9GT-nIKf3-NpNKg5HQp-cNR2EaYLDvdpkzC6YfcCcgjkfN2AekJycXGyv7u5Gk63ec8ZwYNZ15ftMiHSrWy9jONDMNM_Bil2NoBXGzYMMFWxN2QtiHyWZja63AeOaSR3kGaMHctI03DSN_nYOZYX7-0TgF3Q6iJ8jPdiaPqpF-kSTHyHOjbLP_CVuA2-AKs4LaBQTFPC1gNMrYFLNganKkebV_Feh87XwMIEb4CEj5V6KXKvBvxA5n4vyflcbAUV3BaEQ3jewAjcIqnyXWsaDACywDrn9BXeOct3BGeMt4JxVmWmCDPo-1BIz1T8GTZftQgaOz2twvIMdfr4f07RKfhjnvBW4VYgnuEvWAj-waAP_PyGnnpJraNAVyBXTU_qmrWZULWEFM-rhkDP5Z0Zn0TvaJCz6HcernZmM14sl9QImUpytE84UDEKGl1EpwTsBZD9eR4p6Hde4oN4bfaGe6zSdVrfdtWync95xXKdBN9SzXKvZcc7cTrvdabecduu9QV9NzLNm125bZ13XRQOnZaMe-wSv5Jvsh2r-q-9_AaR1L4g)

**Mermaid code:**

```
graph LR
    subgraph Internet
        CDN[Azure CDN<br/>Content Delivery]
    end

    subgraph Azure Region
        direction TB
        ALB[Azure Load Balancer]

        subgraph App Services
            API1[API Instance 1]
            API2[API Instance 2]
        end

        subgraph Data Layer
            SQLP[SQL Primary]
            SQLR[SQL Replica<br/>Read Only]
            BLOB[Blob Storage]
        end

        subgraph Static Content
            SWA[Static Web Apps<br/>React Frontend]
        end
    end

    subgraph Clients
        Browser[User Browser]
        Player1[Display 1]
        Player2[Display 2]
        Player3[Display 3]
    end

    Browser -->|HTTPS| SWA
    SWA -->|API Calls| ALB
    ALB --> API1
    ALB --> API2

    API1 -->|Write| SQLP
    API2 -->|Write| SQLP
    API1 -->|Read| SQLR
    API2 -->|Read| SQLR

    SQLP -.->|Replication| SQLR

    API1 -->|Upload/Download| BLOB
    API2 -->|Upload/Download| BLOB

    BLOB -->|Cache| CDN

    Player1 -->|Schedule/Heartbeat| ALB
    Player2 -->|Schedule/Heartbeat| ALB
    Player3 -->|Schedule/Heartbeat| ALB

    Player1 -->|Media Download| CDN
    Player2 -->|Media Download| CDN
    Player3 -->|Media Download| CDN

    style Browser fill:#e1f5ff
    style Player1 fill:#ffe1e1
    style Player2 fill:#ffe1e1
    style Player3 fill:#ffe1e1
    style SWA fill:#d4edda
    style API1 fill:#cce5ff
    style API2 fill:#cce5ff
    style SQLP fill:#fff3cd
    style SQLR fill:#f8d7da
    style BLOB fill:#e7d4f5
    style CDN fill:#d1ecf1
```
