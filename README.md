![Fork logo](docs/assets/fork_illustration_header.webp)

<div align="center">
  <a href="https://app.forktm.com/">`Try for free`</a> •
  <a href="https://app.forktm.com/help-center">`Help Center`</a>
</div>



**Community-maintained, open-source threat libraries that power [Fork Community Edition](https://forktm.com) for building risk-centric threat models with the
[PASTA]([PASTA](https://versprite.com/blog/what-is-pasta-threat-modeling/)) methodology.**

## Introduction

This repository provides a collaborative space for enhancing and expanding the capabilities of Fork through community contributions. It consolidates previous
work, including the attack trees shared by VerSprite, which are now available for you as industry and technology focused threat libraries.

## What is Fork?

Fork is a SaaS platform that implements the Process for Attack Simulation and Threat Analysis framework for threat modeling. Our goal is to create a tool that
not only serves the needs of security professionals but also evolves with the contributions of the community. The community version is freely available and
designed with extensibility in mind, allowing the community to contribute and enhance various parts. Meanwhile, the enterprise edition aims to cater to
organizations with more advanced functionalities and tailored features.

## Comprehensive Threat Libraries

Each threat library enumerates threats, the motives behind them, the components they target, and the CWEs that make them possible. From those CWEs, Fork
computes the rest of the taxonomy mappings automatically (CAPEC, MITRE ATT&CK and ATLAS, D3FEND, CVE, OWASP ASVS, and NIST SP 800-53) so work here stays focused
on the security analysis rather than on cross-referencing catalogs by hand.

### Industry-focused threat libraries

| Industry               | Threat Library                                                      | Visualization                                                                    |
|------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------|
| Automotive             | [View](industry_focused_threat_libraries/automotive.json)           | [View](industry_focused_threat_libraries/visualization/automotive.md)            |
| Consumer Electronics   | [View](industry_focused_threat_libraries/consumer_electronics.json) | [View](industry_focused_threat_libraries/visualization/consumer_electronics.pdf) |
| Energy                 | [View](industry_focused_threat_libraries/energy.json)               | [View](industry_focused_threat_libraries/visualization/energy.pdf)               |
| Financial              | [View](industry_focused_threat_libraries/financial.json)            | [View](industry_focused_threat_libraries/visualization/financial.pdf)            |
| Fintech - Credit Cards | [View](industry_focused_threat_libraries/fintech-credit-cards.json) | [View](industry_focused_threat_libraries/visualization/fintech-credit-cards.pdf) |
| Government             | [View](industry_focused_threat_libraries/government.json)           | [View](industry_focused_threat_libraries/visualization/government.pdf)           |
| Healthcare             | [View](industry_focused_threat_libraries/healthcare.json)           | [View](industry_focused_threat_libraries/visualization/healthcare.pdf)           |
| Higher Education       | [View](industry_focused_threat_libraries/higher-education.json)     | [View](industry_focused_threat_libraries/visualization/higher-education.md)      |
| Hospitality            | [View](industry_focused_threat_libraries/hospitality.json)          | [View](industry_focused_threat_libraries/visualization/hospitality.md)           |
| Insurance              | [View](industry_focused_threat_libraries/insurance.json)            | [View](industry_focused_threat_libraries/visualization/insurance.pdf)            |
| Manufacturing          | [View](industry_focused_threat_libraries/manufacturing.json)        | [View](industry_focused_threat_libraries/visualization/manufacturing.pdf)        |
| Retail                 | [View](industry_focused_threat_libraries/retail.json)               | [View](industry_focused_threat_libraries/visualization/retail.pdf)               |
| Shipping               | [View](industry_focused_threat_libraries/shipping.json)             | [View](industry_focused_threat_libraries/visualization/shipping.pdf)             |
| Telecommunication      | [View](industry_focused_threat_libraries/telecommunication.json)    | [View](industry_focused_threat_libraries/visualization/telecommunication.pdf)    |
| Transportation         | [View](industry_focused_threat_libraries/transportation.json)       | [View](industry_focused_threat_libraries/visualization/transportation.pdf)       |

### Technology-focused threat libraries

| Technology | Threat Library                                      | Visualization                                                    |
|------------|-----------------------------------------------------|------------------------------------------------------------------|
| AI         | [View](technology_focused_threat_libraries/ai.json) | [View](technology_focused_threat_libraries/visualization/ai.pdf) |

## Holistic Mapping of Taxonomies

Our platform is expanding its scope to encompass mapping all relevant taxonomies. In Fork, we strive to provide a holistic approach by integrating both theory
and evidence methodologies. Fork’s evidence-based approach complements your threat models and helps identify additional Tactics, Techniques, and Procedures
(TTPs) for consideration in the attack tree. These adversarial methods are derived from real-world attacks observed and reported by legitimate sources.

Fork is incorporating threats and adversarial methods derived from multiple categories of observed behavior:

* TTPs used against your Technology Platform(s)
* Software used maliciously against your Industry
* Campaign(s) targeting your Industry

## Repository Objectives

- **Issue Tracker**: A dedicated system for reporting issues, suggesting enhancements, and discussing project-related matters.
- **Community Contributions**: Members can contribute to JSON files that constitute the basis of a threat library, which are integral to Fork's functionality.
- **Automatic Updates**: Changes to the JSON files that pass the peer-review process will be reflected in the platform with each new release, ensuring
  up-to-date threat modeling capabilities.

## Contributing

1. **Clone the Repository**: `git clone git@github.com:VerSprite/forkTM.git`
2. **Explore the JSON Files**: Contribute to our threat libraries to enhance the platform's threat modeling capabilities.
3. **Report Issues or Suggestions**: Use the GitHub Issues tab to report bugs, request features, or discuss the project.
4. **Contribute**: Make changes to the JSON files and submit a pull request. Our team will review and integrate contributions in the next release.

## Contact

For further inquiries or direct communication, please contact [forktm@versprite.com](mailto:forktm@versprite.com).

## Acknowledgments

A special thanks to all the contributors who have made Fork a reality. Your efforts are deeply appreciated!

---

Happy Threat Modeling!

The Fork Team
