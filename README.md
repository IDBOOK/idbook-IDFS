# idbook-IDFS
In the IDBook authentication system, the user's identity information is encrypted by the user's public key information, and relevant valid proof electronic files will be saved to IDFS.


In order to protect users' privacy, the saved file is the original file together with the wallet address after the user's public key encryption. Users can only decrypt the original file by using the correct private.
After the user has saved the appropriate document, a hash fingerprint is generated based on the contents of the file. The user needs to use the public key of the organization to encrypt the file and send it during the authentication process, so that only the organization can decrypt the plaintext for verification. The specific process is shown in the figure below.


In IDFS, all files and block data have a unique fingerprint, which is based on the cryptographic hash algorithm.[6]
The file owner can retrieve the encrypted version from IDFS with the file's fingerprint, and then restore the original version of the file with his private key. Through the content-based file hash fingerprint, even if there is a single byte change in the file, the hash fingerprint will become completely different, ensuring the security of the file.

One of the benefits of using IDFS is that a document is no longer stored centrally. A hash fingerprint will be first generated according to its content, which is used to locate the file in IDFS network. At the same time, large files are cut into small pieces, which can be downloaded from multiple servers at the same time. The IDFS network is an unfixed, fine-grained and distributed network, which can meet the requirements of a content distribution network (CDN). These features also give the IDFS a strong disaster backup feature, because damage to a node will not lead to a missing file. When the IDFS finds file fragments nodes are low, it will automatically increase the number of node storage file fragments.

Considering changing factors of IDFS incentivizes policy in the future, all public networks that save the file through IDFS need to consume a certain Filecoin. In order to avoid IDBook having an incentive model that is easily interfered with by external factors, we decided to use an IDFS modification and have the source be a private network environment. All the IDBook deployment nodes at the same time share the duty of IDFS private network nodes, through interface control, IDBook monitoring file reading and writing, and consuming a certain amount of IDB according to the size of files. The collected IDB will be used to motivate nodes to participate in reading and storage.



