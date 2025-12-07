# Microsoft Entra Connect Security Research

## Project Overview

**Duration**: Summer 2025  
**Organisation**: Reversec UK Ltd  
**Focus**: Microsoft Entra Connect Sync exploitation and credential extraction

During my summer 2025 internship at Reversec, I conducted in-depth research into Microsoft Entra Connect (formerly Azure AD Connect) security, focusing on synchronisation exploitation and identity compromise attack paths.

## Research Focus

### Entra Connect Synchronisation Exploitation

Examined security implications of on-premises to cloud identity synchronisation, specifically:

- MSOL (Microsoft Online) service account credential extraction
- DCSync attack execution in hybrid identity environments
- Lateral movement opportunities in Entra Connect infrastructure
- Attack chain development from initial access to cloud tenant compromise

### Challenges Addressed

**Deprecated Tooling**: Much of the existing Entra Connect attack research relied on AADInternals PowerShell modules that have become outdated. Our research focused on:

- Developing modern alternatives to deprecated functionality
- Creating Graph API-based replacement scripts
- Documenting comprehensive attack methodologies
- Building proof-of-concept tooling for security testing

## Key Achievements

### Technical Development
- Successfully extracted MSOL service account credentials from Entra Connect servers
- Executed DCSync attacks to obtain domain credentials
- Developed modern Graph API scripts replacing legacy AADInternals functions
- Created comprehensive attack guides for penetration testing scenarios

### Collaborative Research
Worked alongside teammate Max to:
- Document attack paths systematically
- Develop reliable exploitation techniques
- Create testing frameworks for hybrid identity security
- Produce practical guidance for security assessments

## Implications

This research highlights critical security considerations for organisations using hybrid identity models:

- The elevated privileges required for Entra Connect synchronisation create significant attack surface
- Compromise of Entra Connect servers can lead to full Azure tenant compromise
- Modern defensive strategies must account for identity synchronisation security
- Regular security assessments of identity infrastructure are essential

## Technical Stack

**Technologies**: 
- Microsoft Entra Connect / Azure AD Connect
- Microsoft Graph API
- Active Directory
- PowerShell
- Windows Server environments

**Attack Techniques**:
- Credential extraction
- DCSync attacks
- Lateral movement
- Privilege escalation
- Cloud tenant compromise

## Skills Demonstrated

- Advanced identity and access management security
- Cloud and hybrid infrastructure exploitation
- Security research and tool development
- Technical documentation and methodology creation
- Collaborative security research

---

!!! warning "Research Context"
    This research was conducted in controlled environments for legitimate security research purposes. All findings were used to improve defensive security practices and are presented here in a sanitised format appropriate for educational purposes.

## Industry Relevance

Understanding Entra Connect security is critical for:
- Penetration testers assessing hybrid environments
- Security teams defending Azure tenants
- Identity security specialists
- Red team operations in cloud environments

This research contributes to the broader understanding of hybrid identity security and practical attack methodologies.
