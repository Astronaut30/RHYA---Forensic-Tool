# RHYA — Secure Data Erasure & Advanced File Recovery Toolkit

<p align="center">
  <img src="assets/rhya-logo.jpeg" alt="RHYA Logo" width="180"/>
  <br><br>
  <b>Integrated Digital Forensics, Advanced File Recovery & Secure Data Sanitization</b>
  <br>
  <i>Smart India Hackathon 2026 — SIH26149</i>
</p>

---

## 🔐 About RHYA

**RHYA** is an integrated digital forensics and data sanitization toolkit designed to address two critical requirements of modern digital investigations:

- **Recovering deleted or lost digital evidence**
- **Securely erasing sensitive data with verification**

Traditional solutions often require separate tools for forensic recovery and secure data erasure. RHYA brings these capabilities together into a **single controlled workflow**, while maintaining evidence integrity through cryptographic hashing, verification, audit logging, and forensic reporting.

> **Recover → Analyze → Erase → Verify → Report**

RHYA is designed for use by digital forensic investigators, law enforcement agencies, forensic laboratories, government organizations, enterprises, and cybersecurity teams.

---

## 🎯 Problem Statement

### SIH26149

**Design and Development of an Integrated Secure Data Erasure and Advanced File Recovery Tool for Digital Forensics and Data Sanitization**

### Core Challenge

Existing tools often separate data recovery and secure erasure, making it difficult to:

- Preserve digital evidence during investigation
- Recover deleted or fragmented files
- Prevent accidental data loss
- Securely sanitize sensitive information
- Verify whether erasure was successful
- Maintain reliable audit records
- Generate structured forensic reports

RHYA addresses these challenges through an integrated and controlled forensic workflow.

---

# 🌟 Key Features

### 🔎 Advanced File Recovery

- Recover deleted and lost files from supported forensic images.
- Perform file-signature based recovery and basic file carving.
- Analyze unallocated storage areas for recoverable evidence.
- Preserve recovered evidence for further forensic analysis.

### 🧹 Secure Data Erasure

- Securely sanitize selected files and storage media.
- Support controlled erasure operations.
- Provide verification of completed sanitization.
- Maintain records of erasure operations for auditing.

### 🔐 Evidence Integrity

- Generate cryptographic hashes for evidence verification.
- Verify file integrity before and after forensic operations.
- Maintain controlled processing of forensic evidence.
- Record important investigation activities in audit logs.

### 📋 Forensic Audit Trail

- Record recovery, analysis, erasure, and verification activities.
- Maintain timestamps and operation details.
- Provide traceable records of important forensic actions.
- Support transparent investigation workflows.

### 📊 Forensic Reporting

- Generate structured reports containing investigation results.
- Include recovery information and verification results.
- Record secure erasure activities.
- Provide a consolidated view of forensic operations.

### 💿 Forensic Image Analysis

- Mount and analyze supported forensic disk images.
- Navigate partitions, directories, and files.
- Examine file metadata and contents.
- Support common forensic image formats.

### 🌳 Tree Viewer

- Navigate the complete structure of a forensic image.
- Browse partitions, directories, and files.
- Quickly locate relevant evidence.
- Display file and folder information in an organized manner.

### 🧬 Detailed File Analysis

Analyze files using multiple representations:

- HEX view
- Text view
- Metadata
- Application-specific views where supported
- File properties and forensic information

### 📷 EXIF Metadata Extraction

- Extract EXIF metadata from supported images.
- Display available information such as timestamps, camera information, and location metadata.
- Assist investigators in analyzing image-based evidence.

### 🪟 Windows Registry Analysis

- Open and examine Windows Registry files.
- Support forensic investigation of registry artifacts.
- Help investigators identify relevant system information.

### 🦠 Malware Analysis Integration

- Optional VirusTotal API integration.
- Submit supported files for malware reputation checking.
- Display available threat intelligence results.

> API access requires a user-provided VirusTotal API key.

### 💾 E01 Image Verification

- Verify the integrity of supported E01 forensic images.
- Detect potential integrity issues during evidence handling.
- Support verification as part of the forensic workflow.

### 🔄 E01 to RAW Conversion

- Convert supported E01 forensic images into RAW format.
- Allow RAW images to be used for further forensic analysis.

### 🔤 Message Decoding

Decode supported encoded messages such as:

- Base64
- Binary
- Other commonly encountered encodings

---

# 🧩 RHYA Workflow

```text
                 ┌─────────────────────┐
                 │   Evidence Input    │
                 │ E01 / RAW / IMG etc.│
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Analysis & Scanning │
                 │  Image / File Scan  │
                 └──────────┬──────────┘
                            │
                 ┌──────────┴──────────┐
                 ▼                     ▼
        ┌──────────────────┐   ┌──────────────────┐
        │  File Recovery   │   │  File Analysis   │
        │ Deleted / Lost   │   │ Metadata / HEX   │
        └────────┬─────────┘   └────────┬─────────┘
                 │                      │
                 └──────────┬───────────┘
                            ▼
                 ┌─────────────────────┐
                 │ Secure Data Erasure │
                 │   Sanitization      │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Verification & Hash │
                 │     Validation      │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Audit Trail & Report│
                 └─────────────────────┘
```

---

# 💾 Supported Forensic Image Formats

| Image Format | Extensions | Split | Unsplit |
|---|---|:---:|:---:|
| EnCase® / Expert Witness Format | `.E01`, `.Ex01` | ✅ | ✅ |
| SMART / Expert Witness Image | `.s01` | ✅ | ✅ |
| RAW / DD Image | `.dd`, `.img`, `.raw` | ✅ | ✅ |
| ISO Image | `.iso` | ❌ | ✅ |
| AccessData Image | `.ad1` | ✅ | ✅ |

> Support may depend on the installed forensic libraries and the specific image structure.

---

# 🗂️ Tested File Systems

| File System | Status |
|---|:---:|
| NTFS | ✅ Tested |
| FAT32 | 🔄 Under Testing |
| exFAT | 🔄 Under Testing |
| HFS+ | 🔄 Under Testing |
| APFS | 🔄 Under Testing |
| EXT2 / EXT3 / EXT4 | 🔄 Under Testing |

---

# 🚀 Getting Started

## ⚙️ Installation — Windows

### Prerequisites

- Windows 10/11
- Python **3.11**
- Microsoft C++ Build Tools
- Git
- Sufficient storage for forensic images and recovered evidence

> Python 3.12 may not be supported by all dependencies used by the project.

### 1. Install Python 3.11

Download Python 3.11 from:

https://www.python.org/downloads/

During installation, enable:

```text
Add Python to PATH
```

### 2. Install Microsoft C++ Build Tools

Required workloads:

```text
Desktop development with C++
C++ build tools
```

### 3. Clone the Repository

```bash
git clone https://github.com/<YOUR-USERNAME>/<YOUR-REPOSITORY>.git
cd RHYA
```

### 4. Create and Activate a Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate
```

### 5. Install Dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 6. Run RHYA

```bash
python main.py
```

---

## 🐧 Linux / Ubuntu / WSL

```bash
python3.11 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python main.py
```

---

## 🍎 macOS

```bash
chmod +x install_macos_linux_WSL.sh
./install_macos_linux_WSL.sh
```

Then:

```bash
source venv/bin/activate
python main.py
```

---

# 🔑 Configuration

## API Keys

Some optional RHYA integrations require external API keys.

### VirusTotal

The VirusTotal integration requires a valid VirusTotal API key.

Configure the API key through the application's API configuration/settings interface, if available.

> Never commit API keys, passwords, tokens, or other secrets to GitHub.

Recommended environment variable:

```text
VIRUSTOTAL_API_KEY=your_api_key_here
```

---

# 🛠️ Technical Approach

RHYA follows a modular forensic workflow:

### 1. Evidence Acquisition
Import supported forensic disk images or storage evidence into the investigation environment.

### 2. Image Analysis
Analyze partitions, file systems, directories, and storage structures.

### 3. Evidence Recovery
Identify and recover deleted or lost files using forensic recovery and file-carving techniques where applicable.

### 4. File Analysis
Inspect recovered or existing files through metadata, hexadecimal, text, and other supported analysis views.

### 5. Secure Data Erasure
Perform controlled data sanitization operations on selected data or supported storage targets.

### 6. Verification
Verify hashes, recovery results, and sanitization results where applicable.

### 7. Audit & Reporting
Record important operations and generate structured forensic reports.

---

# 🧱 Built With

- **Python 3.11** — Core development language
- **PySide6** — Graphical User Interface
- **pytsk3** — Python bindings for The Sleuth Kit
- **libewf / libewf-python** — Expert Witness Format / E01 image access
- **Arsenal Image Mounter** — Forensic image mounting on Windows
- **Cryptographic Hashing** — Evidence integrity verification
- **VirusTotal API** — Optional malware reputation analysis

---

# 📁 Project Structure

```text
RHYA/
│
├── main.py
├── requirements.txt
├── README.md
├── LICENSE
│
├── assets/
│   └── rhya-logo.png
│
├── src/
│   ├── recovery/
│   ├── erasure/
│   ├── analysis/
│   ├── verification/
│   ├── reporting/
│   └── audit/
│
├── tests/
│
└── docs/
```

> The exact structure may differ depending on the implementation of the current RHYA repository.

---

# 🔐 Security & Evidence Integrity

RHYA is designed around controlled forensic handling and evidence integrity.

Important principles include:

- Work on forensic copies whenever appropriate.
- Avoid modifying original evidence.
- Generate hashes for evidence verification.
- Maintain detailed operation records.
- Verify important forensic operations.
- Keep recovered evidence separate from source evidence.
- Protect investigation reports and audit records.

RHYA's sanitization design can be aligned with **NIST SP 800-88 Rev. 2** guidance, depending on the specific implementation and storage technology.

---

# 🚀 Innovation & Uniqueness

RHYA focuses on integrating capabilities commonly handled using separate forensic and sanitization workflows.

### 🔹 Unified Workflow

```text
Digital Forensics
       +
File Recovery
       +
Secure Data Erasure
       +
Verification
       +
Audit Trail
       +
Forensic Reporting
```

### 🔹 Recovery + Sanitization

The platform is designed to support both:

- Recovery of relevant digital evidence
- Secure disposal of sensitive information

within a controlled investigation workflow.

### 🔹 Verification-Based Operations

RHYA emphasizes verification instead of treating an operation as successful simply because a command completed.

### 🔹 Evidence Integrity

Cryptographic hashing and audit records are incorporated into the workflow to support trustworthy evidence handling.

---

# 👥 Target Users

- 👮 Law Enforcement Agencies
- 🔬 Digital Forensic Laboratories
- 🏛️ Government Organizations
- 🏢 Enterprises
- 🛡️ Cybersecurity Teams
- 🎓 Academic & Research Institutions
- 👨‍💻 Digital Forensic Investigators

---

# 💡 Benefits

### For Law Enforcement

- Faster digital evidence recovery
- Structured forensic examination
- Evidence integrity verification
- Centralized investigation workflow

### For Forensic Laboratories

- Unified analysis environment
- Recovery and verification capabilities
- Detailed audit records
- Structured reporting

### For Enterprises

- Secure disposal of sensitive information
- Support for internal investigations
- Reduced dependency on multiple tools

### For Government Organizations

- Controlled handling of sensitive information
- Secure data sanitization workflows
- Improved accountability and traceability

---

# 📈 Future Enhancements

Potential future improvements include:

- 🔹 Advanced AI-assisted file classification
- 🔹 Improved fragmented-file recovery
- 🔹 Additional forensic image formats
- 🔹 Additional file-system support
- 🔹 Advanced timeline analysis
- 🔹 Automated artifact identification
- 🔹 Enhanced malware analysis
- 🔹 Hardware-level sanitization support
- 🔹 Advanced forensic reporting
- 🔹 Role-based access control
- 🔹 Tamper-evident audit storage
- 🔹 Optional distributed/blockchain-based audit verification

> These are future enhancement possibilities and are not presented as currently implemented functionality unless available in the project code.

---

# 🧪 Testing

Before using RHYA with real forensic evidence, test the application using controlled test images and datasets.

Recommended testing areas:

```text
✓ Disk image mounting
✓ Partition detection
✓ File-system parsing
✓ Deleted file recovery
✓ File carving
✓ Metadata extraction
✓ Hash generation
✓ Evidence verification
✓ Secure erasure
✓ Erasure verification
✓ Audit logging
✓ Report generation
```

---

# 🐛 Troubleshooting

### Python version issue

```bash
python --version
```

Recommended:

```text
Python 3.11.x
```

### Virtual environment not activated

Windows:

```bash
venv\Scripts\activate
```

Linux / macOS:

```bash
source venv/bin/activate
```

### Dependency installation failure

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

For packages requiring native compilation on Windows, verify that Microsoft C++ Build Tools are installed.

---

# 🤝 Contributing

Contributions are welcome.

### 1. Create a feature branch

```bash
git checkout -b feature/new-feature
```

### 2. Make and test your changes

### 3. Commit

```bash
git commit -m "Add new forensic feature"
```

### 4. Push

```bash
git push origin feature/new-feature
```

### 5. Create a Pull Request

Please ensure that contributions do not compromise evidence integrity, user privacy, or secure data-handling practices.

---

# 📜 License

This project is developed as part of **Smart India Hackathon 2026**.

Add the project's applicable open-source license here.

Example:

```text
MIT License
```

---

# 🏆 Smart India Hackathon 2026

| Field | Details |
|---|---|
| **Problem Statement ID** | SIH26149 |
| **Problem Statement** | Design and Development of an Integrated Secure Data Erasure and Advanced File Recovery Tool for Digital Forensics and Data Sanitization |
| **Theme** | Blockchain & Cybersecurity |
| **Category** | Software |
| **Project Name** | RHYA |
| **Team Name** | CyberVault |

---

# 📚 Research & References

1. **NIST — SP 800-88 Rev. 2: Guidelines for Media Sanitization**
2. **SWGDE — Best Practices for Digital Evidence Collection**
3. **SWGDE — Best Practices for Computer Forensic Examination**
4. **Microsoft Sysinternals — SDelete**
5. **The Sleuth Kit — Digital Forensic Analysis Tools**
6. **Autopsy — Open Source Digital Forensics Platform**
7. **libewf — Expert Witness Format Library**

---

# ⚠️ Responsible Use

RHYA is intended for **authorized digital-forensics investigations, cybersecurity research, data sanitization, education, and legitimate security operations**.

Users should only analyze or erase data when they have appropriate authorization.

Do not use RHYA to access, modify, recover, or destroy data belonging to others without permission.

---

<p align="center">

### 🔐 RHYA

<b>Recover. Analyze. Erase. Verify. Report.</b>

<br><br>

<i>Building a safer and more accountable digital-forensics workflow.</i>

</p>
