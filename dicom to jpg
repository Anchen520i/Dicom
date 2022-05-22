import os
import pydicom       #用于读取DICOM(DCOM)文件
import argparse
# import scipy.misc    #用imageio替代
import imageio


if __name__ == '__main__':
    parser = argparse.ArgumentParser()
    parser.add_argument('--origin', type=str, default='D:/Download/stage_2_train_images', help='train photos')
    parser.add_argument('--JPG', type=str, default='D:/Download/medic_train', help='test photos')
    opt=parser.parse_args()
    print(opt)


    #imgway_1为源文件夹
    #imgway_2为jpg文件夹
    imgway_1=opt.origin
    imgway_2 = opt.JPG

    i=0

    for filename in os.listdir(r"%s" % imgway_1):

        # name = str(i)
        name=filename[:-4]

        ds = pydicom.read_file("%s/%s" % (imgway_1, filename))          #读取文件

        img = ds.pixel_array

        imageio.imwrite("%s/%s.jpg" % (imgway_2, name), img)

        i+=1

        print("True")

        if i==10000:      #转换10000张
            break
