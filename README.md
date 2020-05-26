# PGP Banking Tuesday, 26/05/2020
Nhiệm vụ của PGP Emulator Server
1. Cung cấp API để RSA Client gọi
=> Viết API truy vấn thông tin (/partner) và API nộp tiền vào tài khoản
*API truy vấn thông tin: Khi RSA gọi API cần cung cấp cái trường:
-ts
-partCode: GO (bankCode của RSA)
-sig: md5(ts + JSON.stringify(req.body) + hashSecretKey) trong đó hashSecretKey = md5("InfymtPGP")
*API nộp tiền vào tài khoản
-ts
-partCode: GO (bankCode của RSA)
-sig: md5(ts + JSON.stringify(req.body) + hashSecretKey) trong đó hashSecretKey = md5("InfymtPGP")
-signature: RSA kí bằng private key của RSA, RSA phải cung cấp publickey cho PGP => process.partnerRSA.RSA_PUBLICKEY

2. (NV phụ) Đóng vai trò Client gọi đến API mà RSA Server cung cấp 