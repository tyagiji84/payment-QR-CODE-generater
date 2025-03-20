# payment-QR-CODE-generater
import qrcode


#taking upi id as a input
upi_id = input("Enter your UPI ID = ")

#upi://pay?=UPI_ID&apn=NAME&am=Amount&cu=CURENCY&tn=MESSAGE

#Defining the payment Url based on the upi id  and the payment app
#Ypu can modify these urls based on the payment apps you want to support

phonepe_url = f"upi:pay?pa={upi_id}&pn=Recipent%20Name&mc=1234"
paytm_url = f"upi:pay?pa={upi_id}&pn=Recipent%20Name&mc=1234"
google_url = f"upi:pay?pa={upi_id}&pn=Recipent%20Name&mc=1234"
#create qr codes for each payement app

phonepe_qr = qrcode.make(phonepe_url)
paytm_qr = qrcode.make(paytm_url)
google_qr = qrcode.make(google_url)

#save the qr code to image file
phonepe_qr.save("phonepe_qr.png")
paytm_qr.save("paytm_qr.png")
google_qr.save("google_qr.png")

#display the qr code
phonepe_qr.show()
paytm_qr.show()
google_qr.show()


