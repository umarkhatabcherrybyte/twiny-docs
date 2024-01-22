# Twiny Mobile Project Documentation

## API Requests

Note :-  For local-host , the base URI is `` however for Production the uri is `https://someURIByUzairBhai/api`.

### 1. **Signup**

- **Type of Request:** POST
- **Endpoint:** /users/signupw3
- **Request Body Pattern:**
    ```json
    {
        "firstName": "Umar",
        "lastName": "Khatab",
        "email": "umarkhatabcherrybyte@gmail.com",
        "password": "123",
        "phone": "0300000"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "user": {
            "firstName": "Umar",
            "email": "umarkhatabcherrybyte@gmail.com",
            "phone": "0300000",
            "address": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63"
        },
        "msg": "OTP is emailed to verify"
    }
    ```

### 2. **Verify Email**

- **Type of Request:** POST
- **Endpoint:** /users/verifyemailw3
- **Request Body Pattern:**
    ```json
    {
        "email": "umarkhatabcherrybyte@gmail.com",
        "otp": "6970"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "user": {
            "firstName": "Umar",
            "lastName": "Khatab",
            "email": "umarkhatabcherrybyte@gmail.com",
            "phone": "0300000",
            "address": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63"
        },
        "msg": "Email verified successfully"
    }
    ```

### 3. **Login**

- **Type of Request:** POST
- **Endpoint:** /users/loginw3
- **Request Body Pattern:**
    ```json
    {
        "email": "umarkhatabcherrybyte@gmail.com",
        "password": "123"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "user": {
            "firstName": "Umar",
            "email": "umarkhatabcherrybyte@gmail.com",
            "phone": "0300000",
            "address": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63"
        },
        "msg": "User LoggedIn successfully",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.[token]"
    }
    ```

### 4. **Does User Exist**

- **Type of Request:** GET
- **Endpoint:** /users/doesUserExists
- **Request Body Pattern:**
    ```json
    {
        "email": "umarkhatabcherrybyte@gmail.com"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "msg": "This email is registered"
    }
    ```

### 5. **Forget Password**

- **Type of Request:** POST
- **Endpoint:** /users/forgetPasswordW3
- **Request Body Pattern:**
    ```json
    {
        "email": "umarkhatabcherrybyte@gmail.com"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "user": {
            "firstName": "Umar",
            "email": "umarkhatabcherrybyte@gmail.com",
            "phone": "0300000",
            "address": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63"
        },
        "msg": "OTP is emailed for password"
    }
    ```

### 6. **Verify Forget Password OTP**

- **Type of Request:** POST
- **Endpoint:** /users/verifyForgetPasswordW3
- **Request Body Pattern:**
    ```json
    {
        "email": "umarkhatabcherrybyte@gmail.com",
        "otp": "3357",
        "newPassword": "11223344"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "msg": "Password updated successfully"
    }
    ```

### 7. **Watch Sold (Manufacturer Use)**

- **Type of Request:** POST
- **Endpoint:** /user-watches/watch-sold
- **Request Body Pattern:**
    ```json
    {
        "owner_email": "umarkhatabcherrybyte@gmail.com",
        "watchId": "7535908782276"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "user": {
            "email": "umarkhatabcherrybyte@gmail.com",
            "watchId": "7535908782276",
            "tokenId": null,
            "_id": "65aa737b754b11208a6806bd",
            "createdAt": "2024-01-19T13:04:59.431Z",
            "updatedAt": "2024-01-19T13:04:59.431Z",
            "__v": 0
        },
        "msg": "Watch registered successfully"
    }
    ```

### 8. **Does Watch Exist**

- **Type of Request:** GET
- **Endpoint:** /user-watches/does-watch-exists
- **Request Body Pattern:**
    ```json
    {
        "owner_email": "umarkhatabcherrybyte@gmail.com",
        "watchId": "7535908782276"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "msg": "This Watch Exists"
    }
    ```

### 9. **Get All User Watches**

- **Type of Request:** GET
- **Endpoint:** /user-watches/get-all-user-watches
- **Request Body Pattern:**
    ```json
    {
        "owner_email": "umarkhatabcherrybyte@gmail.com"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "watches": [
            {
                "_id": "65aa737b754b11208a6806bd",
                "email": "umarkhatabcherrybyte@gmail.com",
                "watchId": "7535908782276",
                "tokenId": null,
                "createdAt": "2024-01-19T13:04:59.431Z",
                "updatedAt": "2024-01-19T13:04:59.431Z",
                "__v": 0
            }
        ],
        "msg": "This Watch Exists"
    }
    ```

### 10. **Add Watch to Blockchain**

- **Type of Request:** POST
- **Endpoint:** /watch/add-watch-w3
- **Request Body Pattern:**
    ```json
    {
        "owner_firstname": "umar",
        "owner_lastname": "khatab",
        "watchId": "7535908782276",
        "owner_email": "umarkhatabcherrybyte@gmail.com"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "mintedCertificate": {
            "certificateID": 51,
            "firstName": "umar",
            "lastName": "khatab",
            "ownerWallet": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63",
            "isMinted": true,
            "watchId": "65aa74ed754b11208a6806cc",
            "clientId": "65aa723a754b11208a6806ad",
            "merchant": "65aa723a754b11208a6806ad",
            "tokenURI": "bafybeignhpqn3ql6gd253zz4lszk6yv52tk3mdoztisopgfwosslcvoxta.ipfs.w3s.link/51.json",
            "mailSent": false,
            "metadata": {
                "case_finishes": "Stainless Steel",
                "case_height": "10 mm",
                "case_strap": "Leather",
                "case_screwed_in_lugs": "Yes",
                "case_diameter": "40 mm",
                "case_water_proofing": "50 meters",
                "case_clasp": "Fold-over Clasp",
                "case_back": "Transparent",
                "dial_glass": "Sapphire Crystal",
                "dial_center_dial": "Silver",
                "dial_complication": "Date Display",
                "dial_exterior_elevation": "Embossed",
                "dial_hands": "Luminous",
                "crown_info": "Screw-down Crown",
                "crown_material": "Stainless Steel",
                "movement_automatic": "Yes",
                "movement_access": "Bottom",
                "guarantee_purchase_date": "2024-01-11",
                "guarantee_purchase_time": "12 months",
                "guarantee_statement": "1 Year Limited Warranty",
                "ownerAddress": "0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63",
                "imageURI": "https://cdn.shopify.com/s/files/1/0634/7499/1300/files/rolex_submariner_date.jpg?v=1704453234",
                "name": "Twiny1"
            },
            "pdfIPFSURI": "",
            "_id": "65aa7534754b11208a6806d2",
            "createdAt": "2024-01-19T13:12:20.640Z",
            "updatedAt": "2024-01-19T13:12:20.640Z",
            "__v": 0
        },
        "msg": "Token ID 51 successfully minted for 0x6720BaC0CbDEb95BE7e2ADdE46e23B888059Fd63"
    }
    ```

### 11. **Transfer Watch**

- **Type of Request:** POST
- **Endpoint:** /watch/transfer-watch-w3
- **Request Body Pattern:**
    ```json
    {
        "owner_email": "umarkhatabcherrybyte@gmail.com",
        "receiver": "l192765@lhr.nu.edu.pk",
        "watchId": "7535908782276"
    }
    ```
- **Response:**
    ```json
    {
        "success": true,
        "transferredTo": "0x0276a202cE01b0A4188B011CFD0C52b7f9179187",
        "msg": "Token ID 51 successfully Transferred to l192765@lhr.nu.edu.pk"
    }
    ```
