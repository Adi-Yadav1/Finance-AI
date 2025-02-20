# Finance-AI
DATABASE_URL=postgresql://...
SESSION_SECRET=your_secret_key
```

2. Install Dependencies:
```bash
pip install -r requirements.txt
```

3. Database Setup:
The application will automatically set up the database tables on first run.
Database uses SSL connection for enhanced security.

4. Run the Application:
```bash
python main.py
```

## API Integration

### PAN Verification API
- Endpoint: `https://pan-verify-api-app.onrender.com/verify_pan`
- Method: POST
- Request Format:
  ```
  Key: pan_number → Type: Text → Value: ABCDE1234F
  Key: pan_card → Type: File → Upload: PAN card image
  Key: person_image → Type: File → Upload: Selfie image
  ```
- Response Format:
  ```json
  {
      "verified": true,
      "message": "PAN number and face matched"
  }
  ```

## User Workflows

### Individual Users
1. Register/Login
2. Complete KYC verification
   - Upload PAN card
   - Take selfie for face verification
3. Transfer money
4. View transaction history

### Business Users
1. Register/Login
2. Complete KYB verification
3. Apply for loans
4. Track loan status

### Admin Users
1. Review KYC/KYB applications
2. Approve/Reject loans
3. Monitor transactions
4. View database records

## Security Features

- Password hashing using Werkzeug
- SSL database connections
- File upload validation
- Session management
- Input validation and sanitization

## Project Structure

```
├── routes/
│   ├── admin.py
│   ├── auth.py
│   ├── business.py
│   └── individual.py
├── templates/
│   ├── admin/
│   ├── business/
│   ├── individual/
│   └── base.html
├── static/
│   ├── css/
│   └── js/
├── models.py
├── config.py
└── main.py
