from PIL import Image
#you can use a jpeg and png image
image = Image.open("your_image.png")

def gris(img):
    largeur, hauteur = img.size
    new_img = Image.new('L', img.size)
    for ligne in range(hauteur):
        for pixel in range(largeur):
            R,V,B = img.getpixel((pixel, ligne ))
            G = (R + V + B) // 3
            new_img.putpixel((pixel, ligne), G)
    return new_img

image_gris = gris(image)

def redimensionner(img,largeur,hauteur):
    largeur_img, hauteur_img = img.size
    new_img = Image.new('L', (largeur, hauteur))
    largeur_pix = largeur_img // largeur
    hauteur_pix = hauteur_img // hauteur
    for y_new in range(hauteur):
        for x_new in range(largeur):
            moyenne = 0
            for y in range(hauteur_pix * y_new, hauteur_pix * y_new + hauteur_pix):
                for x in range(largeur_pix * x_new, largeur_pix * x_new + largeur_pix):
                    moyenne = moyenne + img.getpixel((x,y))
            moyenne = moyenne // (largeur_pix * hauteur_pix)
            new_img.putpixel((x_new, y_new),moyenne)
    return new_img

image_redim = redimensionner(image_gris,50,50)


def ascii_art(img):
    caracteres = "@#$%WAL/:- " #you can add or modify the char if you want
    largeur, hauteur = img.size
    sortie = ""
    for y in range(0,hauteur):
        for x in range(largeur):
            pixel = img.getpixel((x,y))
            position = ((len(caracteres)-1) * pixel) // 255
            sortie += caracteres[position]*2
        sortie += "\n"
    return sortie

texte = ascii_art(image_redim)
print(texte)


