!pip install qrcode[pil]
import qrcode
from PIL import Image
from IPython.display import display
import qrcode
from PIL import Image

def generate_qr_code(data):
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_H,
        box_size=10,
        border=4,
    )
    qr.add_data(data)
    qr.make(fit=True)
    img = qr.make_image(fill='black', back_color='white')
    display(img)

# Example usage
data = "https://www.behance.net/manasius"
generate_qr_code(data)
