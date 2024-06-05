# Information Security Notes


---
1. ***Information Security vs. Cybersecurity***
	- **Information Security:**
		Information security is a *broader* *term* that encompasses the protection of *all forms of information*, whether it's in *digital* or *physical form*. It involves safeguarding the *confidentiality*, *integrity*, and *availability* of data. Information security addresses risks related to the unauthorized *access*, *use*, *disclosure*, *disruption*, *modification*, or *destruction* of information. It encompasses not only digital data but also *paper* *documents*, *conversations*, and *other* *forms* *of* *information* *exchange*.
	- **Cyber Security:**
		Cybersecurity, on the other hand, is a *subset* *of information security* that specifically deals with the *protection of digital information* from *cyber threats*. It focuses on *defending* *computer systems*, *networks*, and *digital data* from *attacks*, *breaches*, and *unauthorized* *access*. Cybersecurity includes *measures* such as *antivirus* *software*, *firewalls*, *intrusion* *detection systems*, *encryption*, and *secure coding practices*. It deals primarily with the *protection of digital assets* and the technologies that support them.
---
2. ***Regulatory Compliance: Adhering to specific regulations such as "GDPR" and "HIPAA" to handle sensitive data***
	Regulatory compliance refers to the process of ensuring that an organization follows *laws*, *regulations*, *guidelines*, and *specifications* relevant to its business activities.
	* **GDPR (General Data Protection Regulation):**
		It governs the *processing* and *protection* of *personal data* of individuals within the *Europe Union*. GDPR imposes strict requirements on organizations regarding the *collection*, *storage*, *processing*, and *transfer* of personal data. Organizations must obtain *consent* from individuals to process their personal data, and they are required to implement appropriate technical and organizational measures to ensure data protection and security.
	- **HIPAA (Health Insurance Portability and Accountability Act):**
		HIPAA applies to *healthcare providers*, *health plans*, *healthcare clearinghouses*, and their business associates that handle *protected health information (PHI)*. The law includes provisions for *safeguarding PHI*, ensuring the *confidentiality* of *medical records*, and enabling the *portability* of *health insurance* coverage.
---
3. ***Incident Response and Business Continuity: Developing plans to address data breaches and ensure operational continuity***
	Developing robust incident response and business continuity plans is crucial for organizations to effectively address data breaches and ensure operational continuity.
	* **Incident Response Plan:**
		1. *Preparation:* This involves *identifying* potential *threats* and *vulnerabilities*, establishing *roles* and *responsibilities* for incident response team members, and creating communication channels for reporting incidents.
		2. *Detection and Analysis:* Organizations should have mechanisms in *place* to detect *security incidents* promptly. This could involve *security monitoring tools*, *intrusion detection systems*, and *employee reporting mechanisms*. Once an incident is detected, it's essential to *analyze* its *scope*, *impact*, and *root cause*.
		3. *Containment, eradication and recovery:* After identifying the nature and scope of the incident, the response team works to *contain* the *breach* and prevent further damage. This may involve *isolating affected systems*, *removing* *malicious* *software*, and *restoring data from backups*. Once the incident is contained and the immediate *threats are addressed*, the focus shifts to *restoring affected systems* and services to normal operations. This may involve *reinstalling software*, *restoring data from backups*, and *implementing additional security* measures to prevent future incidents.
		4. *Post-incident activity:* After the incident is resolved, it's essential to conduct a *post-incident review* to identify *lessons learned*, *improve response procedures*, and *strengthen defenses* against future incidents.
	- **Business Continuity Plan (BCP):**
		1. *Risk Assessment and Business Impact Analysis:* Organizations should assess potential *threats* and *vulnerabilities* that could disrupt operations and conduct a business impact analysis to prioritize critical functions and resources.
		2. *Response and Recovery Strategies:* This involves developing strategies and procedures for *maintaining* *essential* *functions* during a *disruption*, such as *alternative work arrangements*, *backup facilities*, and *redundant systems*.
		3. *Plan Development and Implementation:* Once response and recovery strategies are developed, organizations should document them in a *formal business continuity* *plan* and ensure that relevant personnel are *trained* and *familiar* with the plan.
		4. *Testing and Exercise:* Regular *testing* and *exercises* are essential to validate the *effectiveness* of the business continuity plan and identify areas for *improvement*. This may involve tabletop exercises, simulations, or full-scale drills.
		5. *Maintenance and Review:* Business continuity plans should be regularly reviewed and updated to reflect changes in the organization's operations, technology, and risk landscape.
---
4. ***Third-Party Risk Management: Managing risks associated with third-party vendors accessing sensitive data***
	Third-party risk management involves assessing and mitigating the potential risks that arise from the use of third-party *vendors*, *suppliers*, *contractors*, or *partners* who have access to an organization's sensitive *data* or *perform services on its behalf*.
	1. *Risk Assessment:* Begin by identifying and assessing the potential risks associated with third-party relationships. Evaluate the nature and scope of the services provided by third parties, the type of data they have access to, their security practices, and their regulatory compliance posture.
	2. *Contractual Protections*: Establish clear contractual agreements with third-party vendors that outline the *responsibilities*, *obligations*, and *expectations* of both parties regarding data security and privacy. Include provisions for data protection, *confidentiality*, *security standards*, *breach notification requirements*, *indemnification*, and *audit rights.*
	3. *Security Controls and Monitoring:* Require third-party vendors to implement adequate security controls and measures to protect sensitive data. This may include *encryption*, *access controls*, *regular security assessments*, and *monitoring* of vendor activities. Implement mechanisms to continuously monitor third-party compliance with security requirements and promptly address any *non-compliance* issues.
	4. *Data Access and Sharing Controls:* Limit third-party access to sensitive data to only what is necessary for the performance of their services. Implement controls such as *role-based access*, *least privilege principles*, and *data encryption* to restrict access and minimize the risk of unauthorized data exposure.
	5. *Continual Monitoring and Review:* Regularly review and assess the *effectiveness* of third-party risk management processes and controls. Conduct *periodic audits*, *assessments*, and *reviews* of third-party vendors to ensure ongoing compliance with *contractual obligations* and *regulatory requirements.* Update risk assessments and mitigation strategies based on changes in the risk landscape or business environment.
---
5. ***Compliance Reporting and Documentation: Meeting documentation requirements to demonstrate regulatory compliance.***
	Compliance reporting and documentation are essential components of *demonstrating regulatory adherence.* This process involves understanding *relevant rules and regulations*, *documenting comprehensive policies and procedures*, *maintaining accurate records of compliance activities*, *generating compliance reports*, *implementing internal controls*, *adhering to documentation standards*, *retaining documentation based on retention policies*, *maintaining an audit trail of changes*, *submitting external reports as required*, and *continuously improving documentation practices to reflect changes in regulations and business operations*. Through these measures, organizations can effectively demonstrate compliance with regulatory requirements and mitigate associated risks.
---
6. ***International Data Transfers: Addressing challenges in lawful data transfers across borders.***
	1. *Legal Compliance:* Organizations must ensure compliance with data *protection laws* and regulations in both the *originating and destination countries*. This may involve *understanding the requirements of laws* such as the General Data Protection Regulation (GDPR) in the European Union.
	2. *Data Privacy and Security:* Protecting the privacy and security of data during international transfers is most important. Organizations must implement appropriate *technical* and *organizational* measures to safeguard data against unauthorized *access*, *disclosure*, or *misuse*.
	3. *Cross-Border Data Flow Restrictions:* Certain *countries restrict* or regulate the flow of data across their borders for national security. Organizations must understand these restrictions and obtain any *necessary approvals* or *licenses* to facilitate lawful data transfers.
	4. *Data Transfer Mechanisms:* Selecting *appropriate data transfer mechanisms* is crucial for lawful international data transfers. This may include mechanisms such as *SCCs*, *BCRs*, adequacy decisions, derogations for specific situations, or other lawful mechanisms recognized by *relevant regulatory authorities*.
---
7. ***One-time pad in cryptography***
	A one-time pad is a *cryptographic technique used to encrypt and decrypt messages*. It is considered one of the *most secure* encryption methods when implemented correctly. The key used in a *one-time pad* must be truly *random*, *completely secret*, and used only once for each message. Hence, the name **"one-time pad."** If these conditions are met, the resulting ciphertext is theoretically *unbreakable* through *cryptanalysis*. This is because, without knowledge of the exact key used, there is *no statistical pattern* or *information leakage* that an attacker can exploit to decrypt the message.
---
8. ***S-DES (Simplified Data Encryption Standard)***
	**Key**:
	- 10 bits
	- Apply P-10.
	- Separate into left and right.
	- Play 1-left circular shift on both the parts.
	- Apply P-8 on the right side. (padding)
	- The result would be *key1*
	- Again divide into two parts.
	- Apply 2-left circular shift to the right.
	- Apply P-8 on the right one. (padding)
	- The result would be *key2*
	**Text:**
	- 8 bits
	- Apply P-10
	- Divide into left and right.
	- Apply E-P on the right side (padding)
	- Now *XOR* it with *key1*
	- There will be two 4-bit sets.
	- The first four are for *S0* and the second four are for *S1*
	- The *first and the last* bit of the bit-set is for rows and the middle *two* bits are for columns.
	- Apply P-4
	- 
---
9. ***Importance of Images in Information Security***
	1. *Steganography:* Steganography is the practice of *hiding secret information within digital images* or *other media files*. Images can be used as *carriers* to conceal sensitive data, such as *text*, *documents*, or other *images*, without arousing suspicion. Steganography techniques can be employed for covert communication and data exfiltration, making it important for information security professionals to be aware of and mitigate this threat.
	2. *Malware Detection:* Images can be used as *carriers for malware*, such as *trojans* or *ransomware*, through techniques like *steganography* or *image-based exploits*. Security tools and techniques are required to *detect* and *mitigate* *image-based threats*, including the use of *antivirus software*, *intrusion detection* systems, and secure coding practices to prevent *image-based vulnerabilities and attacks.*
	3. *Digital Forensics:* Images are valuable sources of *evidence* in *digital forensic* investigations. Digital images captured from *surveillance cameras*, *smartphones*, or other *devices* can provide *insights into security incidents*, *criminal* *activities*, or *data breaches*. Forensic analysts use image analysis techniques to examine digital images, *extract metadata*, and reconstruct events to support legal proceedings and incident response efforts.
---
10. ***Image Encryption Methods and Techniques***
	1. *Symmetric Encryption:* Symmetric encryption algorithms, such as *AES (Advanced Encryption Standard)* or *DES (Data Encryption Standard),* use a *single key* for both encryption and decryption. In image encryption, symmetric encryption can be applied directly to the *pixel values* of the image.
	2. *Block Cipher Modes of Operation:* Block cipher modes of operation, *CBC (Cipher Block Chaining)* can be used to encrypt images by dividing them into *fixed-size blocks* and applying encryption to each block individually. *CBC* mode is commonly used for image encryption because it provides *better security against certain attacks*, such as *watermarking attacks*.
	3. *Chaotic Encryption:* Chaotic encryption techniques use *chaotic systems* to provide *randomness* for encryption. *Chaos-based* *encryption* methods like *Arnold Transform Encryption*, use chaotic maps or transformations to *scramble the pixel values of images,* making them difficult to decrypt without knowledge of the encryption parameters.
	4. *Hybrid Encryption:* Hybrid encryption *combines symmetric and asymmetric* encryption techniques to leverage the benefits of both. In image encryption, a hybrid approach may involve *encrypting the image using a symmetric algorithm* and *then encrypting the symmetric key with an asymmetric algorithm* for *secure key exchange*.
---
11. ***Confusion and Diffusion in Encryption***
    - ***Confusion:*** 
	    Confusion refers to the process of *hide* the relationship between the *plaintext* and the *ciphertext* in an encryption scheme. Confusion ensures that even *small changes* in the *plaintext* result in *significant changes in the ciphertext.* Confusion aims to make it *difficult* for an *attacker* to *guess or find* any *patterns* or *correlations* between the *plaintext and ciphertext*, thereby enhancing the security of the encryption algorithm.
	- ***Diffusion:***
		Diffusion ensures that *changes* *in one part* of the *plaintext* affect the *entire ciphertext.* This is typically achieved by *mixing* the *plaintext* with the *encryption key* and performing multiple rounds of cryptographic operations, such as *bitwise XOR*, *addition*, or *substitution*, to *distribute* the *influence* of each *plaintext symbol across the entire ciphertext.* This prevents like frequency analysis from happening. 
---
12. ***Chaotic Maps in Cryptography***
	1. *Pseudo-Random Number Generation:* Chaotic maps can serve as *pseudo-random number generators* in cryptographic applications. The chaotic behavior of the map ensures that the generated sequence of numbers appears *random* and *unpredictable*. These pseudo-random numbers can be used to generate *cryptographic keys*, *initialization vectors*, or *nonces* in various *cryptographic protocols*.
	2. *Encryption:* Chaotic maps can be used directly as *components* of encryption algorithms. The chaotic behavior of the map can be exploited to perform *non-linear transformations on plaintext data*, thereby enhancing the security of the *encryption* *process*. For example, chaotic maps can be used to generate *confusion and diffusion* in the encryption process, making it more *resistant to cryptanalysis*.
	3. *Image Encryption:* Chaotic maps are particularly suitable for image encryption due to their ability to introduce *randomness* and *complexity* into the encryption process. Chaotic maps can be used to *permute pixel positions*, *scramble pixel values*, or *generate encryption keys for encrypting digital images*. This helps in achieving *robust encryption schemes* that are resistant to *various attacks*, such as *differential attacks* or *statistical attacks*.
	4. *Digital Signatures:* Chaotic maps can be used to generate digital signatures in cryptographic protocols. By applying chaotic maps to *input data and secret keys*, *unique signatures* can be generated that are difficult to *forge or reproduce* without knowledge of the *secret keys*.
---
13. ***Logistic Map and its Security Applications***
	The logistic map, a simple mathematical model of population growth, has found applications in various fields, including cryptography and information security.
	1. *Pseudo-Random Number Generation:* The logistic map exhibits *chaotic behavior* for certain *parameter values*, making it suitable for *generating pseudo-random* numbers. By iterating the logistic map equation starting from an *initial condition (seed)*, a sequence of *seemingly random* *numbers* can be produced.
	2. *Image Encryption:* As the logistic map has the *chaotic behavior* so it can be used for *image encryption* as well. When the logistic map is used in any of the image encryption algorithm it uses its chaotic nature to *permute* or *shuffle up* the image pixels, in this way the image gets encrypted. Due to this *chaotic nature* logistic map based encryption algorithms are consider *secure*.
	3. *Secure Communication Protocols:* Chaotic maps, including the *logistic map*, have been integrated into secure *communication protocols* to enhance *privacy* and *confidentiality*. By incorporating chaotic maps into encryption and key exchange mechanisms, secure communication channels can be established that are resistant to *eavesdropping* and *interception*.
---
14. ***Substitution Box (S-Box) in Cryptography***
	In cryptography, a *Substitution Box (S-box)* is an important component in many block cipher algorithms like *DES* and *AES*. S-boxes are essential for introducing *confusion* into encryption algorithms, as they *hide the relationship between plaintext and ciphertext*, making it challenging for attackers to discern patterns or correlations in the encrypted data. Their non-linear behavior ensures *resistance* against *linear cryptanalysis* and other known attacks, enhancing the security of the encryption process. Furthermore, S-boxes exhibit key dependence, with each S-box typically *relying* on a *specific encryption key* or *key schedule*, adding an additional layer of security to the cipher. By dispersing the influence of each input bit across multiple output bits, S-boxes contribute to the *avalanche effect*, *where minor changes in input lead to substantial changes in output*, thereby enhancing the *diffusion* of information throughout the cipher's state and reinforcing its security. Overall, S-boxes are critical components of modern cryptographic algorithms, contributing significantly to their resilience against *cryptanalytic attacks*.
---
15. ***Nonlinearity in Encryption Algorithms***
	Nonlinearity is a *fundamental property* in encryption algorithms crucial for enhancing their security. In encryption, *nonlinearity refers to the lack of a simple, linear relationship between the input and output of the cryptographic function*. This nonlinearity *ensures that even small changes in the input, such as a single bit flip, result in significant changes in the output*, thereby introducing *confusion* into the encryption process. Nonlinear transformations, such as substitution operations performed by *Substitution Boxes (S-boxes)* in block ciphers like **AES** and **DES**, play a vital role in hiding the relationship between plaintext and ciphertext. This nonlinearity is essential for resisting various *cryptanalytic attacks*, including linear and differential cryptanalysis, which *exploit linear relationships* between plaintext, ciphertext, and encryption keys. By incorporating nonlinear components into encryption algorithms, such as S-boxes, nonlinearity *enhances the complexity and unpredictability* of the encryption process, contributing to the overall security of the *cryptographic scheme*. Therefore, nonlinearity is a *fundamental aspect* of encryption algorithms that helps protect sensitive information from unauthorized access and *ensures the confidentiality* and integrity of encrypted data.
---
16. ***Cryptographic Hash Functions and their Properties***
	Cryptographic hash functions are *essential cryptographic tools* used for a variety of purposes, including *data integrity verification*, *digital signatures*, *password storage*, and more. These functions take an input `message` and produce a fixed-size `string` of characters, known as the *hash value* or *hash digest*.
	- Here are some of the feathers of a cryptographic hash function.
		- Fast computation.
		- Collision Resistance.
		- Fixed Output Size
		- Avalanche Effect
		- Non-Reversibility
---
17. ***Hashing algorithms in Public Key Cryptography (PKC) and digital signature***
	- **Data Integrity:**
		Before creating a digital signature, the data to be signed is typically *hashed* using a *cryptographic* *hash* *function*. The hash value serves as a *compact* and *unique* representation of the *original* *data*. This *hashed* *value* is what is actually *signed*, rather than the *entire* *data* *itself*. By hashing the data before signing, any *modifications* or *tampering* with the *original* *data* will result in a *completely* *different* *hash* *value*, thus *ensuring* *data* *integrity*.
	* **Efficiency:**
		Hashing algorithms provide an *efficient* means of *processing* *large* *amounts* of data into *fixed size* *hash* *values*. This is particularly useful in *digital signature schemes*, where signing the entire data directly may be *inefficient* or *impractical*, especially for large files or messages. By hashing the data first, digital signatures can be generated and verified more efficiently.
	- **Authentication:**
		When verifying a digital signature, the recipient of the *signed data hashes* the received data using the *same* *hash* *function* used by the *signer*. The *recipient* then *compares* this hash value to the hash value included in the *digital* *signature*. If the two hash values match, it provides *assurance* that the *signed* *data* has not been *tampered* with and originates from the *legitimate* *signer*.
---
18. ***Encryption Key Generation and Management***
	* **Key Generation:**
		- Encryption keys should be generated using a *reliable source of randomness* to ensure their unpredictability.
		- Longer keys generally provide stronger security. The appropriate key length depends on the cryptographic algorithm being used and the level of security required. Common key lengths range from *128 bits to 256 bits* *for symmetric encryption and even longer for asymmetric encryption.*
	- **Key Management:**
		* Encryption keys should be stored securely to prevent *unauthorized access*. Keys should be protected against *physical* *theft*, *unauthorized* *copying*, and *insider* *threats*.
		* *Secure* *distribution* of encryption keys to authorized parties is crucial for enabling secure communication. Key exchange protocols, such as *Diffie-Hellman* *key* *exchange* *or* *key distribution centers (KDCs),* can be used to securely share keys between parties.
		* *Continuous* *monitoring* of key *usage*, *access* *logs*, and *key* *lifecycle* *events* is essential for detecting and responding to *potential* *security* *incidents* or *unauthorized* activities. *Regular* *audits* help ensure compliance with security policies and regulatory requirements
---
19. ***Correlation coefficient and its use in analysis of cryptographic algorithm***
	**The correlation coefficient is a statistical measure that quantifies the degree of linear relationship between two variables.** In the context of cryptographic algorithms, the correlation coefficient can be used in various ways to analyze and evaluate their performance, particularly in cryptanalysis.
	- **Linear Cryptanalysis:**
		The correlation coefficient can be used to measure the linear relationship between the plaintext, ciphertext, and key bits in a cryptographic algorithm. By analyzing the correlation between plaintext bits, ciphertext bits, and key bits, cryptanalysts can identify linear approximations that can be exploited to recover the encryption key.
	- **S-Box Analysis:**
		The correlation coefficient can be used to analyze the non-linear behavior of S-boxes by measuring the correlation between input and output bits. By examining the correlation between input and output bits of S-boxes, cryptanalysts can assess their resistance against linear and differential cryptanalysis attacks.
	- **Cryptographic Hash Functions:** 
		In the analysis of cryptographic hash functions, the correlation coefficient can be used to evaluate the distribution of hash values to assess their properties, such as *randomness* and *uniformity*. By measuring the correlation between input data and output hash values, cryptanalysts can identify any patterns or biases in the hash function's behavior that may indicate weaknesses or vulnerabilities.
---
20. ***Information Entropy***
	It is a concept that originated from *information theory*. The information entropy is the amount of randomness in a set of data. In essence, *higher entropy indicates greater unpredictability*, while *lower entropy suggests more predictability* or regularity. Information entropy is often calculated using **Shannon's entropy formula**, which considers the probabilities of different outcomes within a given data set. For example, in a fair coin toss, where heads and tails are equally likely, the entropy is at its maximum because the outcome is highly uncertain. Higher entropy in *cryptographic keys* indicates greater *randomness* and makes them more *resistant* to *brute-force attacks*, where adversaries attempt to guess the key through exhaustive trial and error.
---
21. ***Security implications of quantum computing on traditional cryptographic schemes***
	The development of quantum computing poses significant security implications for traditional cryptographic schemes, particularly those based on computational complexity assumptions.
	1. *Breaking Public Key Cryptography:* Quantum computers have the potential to break widely used public key cryptographic algorithms, such as `RSA` and `ECC`, through *Shor's algorithm*. This algorithm exploits the quantum properties of superposition and entanglement to efficiently factor large integers and solve the discrete logarithm problem, upon which these cryptographic schemes rely for security. As a result, sensitive communications encrypted using these algorithms could be vulnerable to decryption by quantum adversaries.
	2. *Threat to Symmetric Key Cryptography:* Quantum computers also pose a threat to symmetric key cryptographic algorithms, although to a lesser extent compared to public key cryptography. *Grover's algorithm*, a quantum algorithm, can search through unsorted databases quadratically faster than classical algorithms. This means that the effective key size required to resist *brute-force attacks* is halved for symmetric key algorithms. For example, AES-256, considered secure against classical computers, would offer only 128-bit security against quantum adversaries.
	3. *Challenges in Post-Quantum Cryptography Adoption:* The security implications of quantum computing have led to increased research in post-quantum cryptography (PQC), which aims to develop cryptographic algorithms that remain secure in the presence of quantum computers. However, transitioning to PQC involves challenges such as algorithm *standardization*, *interoperability*, and *performance* *considerations*. Furthermore, existing systems and infrastructures reliant on traditional cryptographic schemes may face security risks during the transition period.
---
22. ***Symmetric encryption algorithms***
	1. **Advanced Encryption Standard (AES):** 
		`AES` is a widely adopted symmetric encryption algorithm standardized by the National Institute of Standards and Technology (NIST). It supports key sizes of `128`, `192`, and `256` bits and operates on fixed-size blocks of data. `AES` has been extensively analyzed and is considered secure for a wide range of applications.
	3. **Data Encryption Standard (DES):** 
		`DES` was one of the earliest symmetric encryption algorithms standardized by NIST in the 1970s. It operates on `64-bit` blocks of data and uses a `56-bit` key. Due to its small key size, `DES` is now considered insecure against modern cryptographic attacks. However, it served as the basis for the development of more secure algorithms such as `AES`.
	5. **Triple DES (3DES):** 
		`3DES` is a variant of `DES` that applies the `DES` algorithm three times in succession with different keys. This provides increased security compared to `DES`, although it is significantly slower due to multiple rounds of encryption. While `3DES` is still used in some legacy systems, it is generally being phased out in favor of `AES`.
---
23. ***Block cipher vs. stream cipher***
	 **Data Processing:**
	-  *Block Cipher:* Operates on fixed-size blocks of data, encrypting each block individually with the same key.
	- *Stream Cipher:* Encrypts data bit by bit or byte by byte, producing a continuous stream of ciphertext.
	**Encryption Mechanism:**
	- *Block Cipher:* Encrypts data by dividing it into fixed-size blocks and applying complex permutations and substitutions to each block.
	- *Stream Cipher:* Generates a pseudo-random keystream, which is combined with the plaintext using bitwise XOR operation to produce ciphertext.
	**Performance:**
	- *Block Cipher:* May be slower for real-time applications due to processing data in fixed-size blocks.
	- *Stream Cipher:* Generally faster and more efficient for encrypting real-time data streams, such as network communication or audio/video transmission.
---
24. ***Access controls and their purposes***
	1. **Role-Based Access Control (RBAC):**
	    - *Purpose*: RBAC assigns permissions to roles rather than individual users. Users are then assigned roles based on their job functions or responsibilities. This simplifies access management by centralizing permissions at the role level and allows for easier administration of access rights, especially in large organizations with complex access requirements.
	2. **Attribute-Based Access Control (ABAC):**
	    - *Purpose*: ABAC evaluates access decisions based on multiple attributes associated with users, resources, and environmental conditions. These attributes can include user roles, department, time of access, location, and more. ABAC provides fine-grained access control and dynamic policy enforcement based on contextual information.
	3. **Rule-Based Access Control (RBAC):**
	    - *Purpose*: RBAC uses rules or policies to determine access permissions. These rules define conditions under which access is granted or denied based on factors such as user attributes, resource attributes, and environmental factors. RBAC enables flexible access control decisions based on predefined rules.
---
25. ***Random Number Generators***
	**Pseudo-Random Number Generators (PRNGs):**
	- PRNGs generate sequences of numbers that appear random but are actually deterministic, meaning that the same seed value will produce the same sequence of numbers.
	- They are initialized with a seed value, which acts as the starting point for generating subsequent numbers.
	- PRNGs are widely used in software applications due to their efficiency and convenience. However, they are not suitable for cryptographic applications where true randomness is required.
---
