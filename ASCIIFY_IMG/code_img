from PIL import Image, ImageDraw, ImageFont

import math

chars = "ASCIIASCIIASCIIASCIIASCIIASCIIASCIIASCIIASCIIASCIIASCIIASCII"[::-1]

charARRAY = list(chars)
charLength = len(charARRAY)
intervals = charLength/256


oneCharWidth = 6
oneCharHeight = 9

def getChar(inputInt):
    return charARRAY[math.floor(inputInt*intervals)]

text_file = open("D:\\Python projects\\ASCII Generator\\ASCII_text.txt", "w")

im = Image.open("D:\Web Development\images\mercedes.jpg")

fnt = ImageFont.truetype('D:\\Python projects\\ASCII Generator\\ascii_font.ttf', 15)

width, height = im.size
im = im.resize((int(0.75*width), int(0.75*height*(6/oneCharHeight))), Image.Resampling.NEAREST)
#CHECKING AND DOING
width, height = im.size
pix = im.load()

#CONVERTING INTO IMG
outputImage = Image.new("RGB", (int(6 * width), int(9 * height)), color = (1, 1, 1))
#USING IMAGE DRAW
d = ImageDraw.Draw(outputImage)

for i in range(height):
    for j in range(width):
        r, g, b = pix[j, i]
        h = int(r/3 + g/3 + b/3)
        pix[j, i] = (h, h, h)
        text_file.write(getChar(h))
        d.text((j*6, i*9), getChar(h), font = fnt, fill = (r, g, b))

    text_file.write('\n')

outputImage.save('ASCII_ART.jpg')

