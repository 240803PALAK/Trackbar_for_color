# Trackbar_for_color
Trackbar for R,G.B to produce new color.

    import cv2
    import numpy as np
    img=np.zeros((512,512,3),np.uint8)
    
    def passfunction(*args):
        pass
    
    cv2.namedWindow('trackbar')
    cv2.createTrackbar('B','trackbar',0,255,passfunction)
    cv2.createTrackbar('G','trackbar',0,255,passfunction)
    cv2.createTrackbar('R','trackbar',0,255,passfunction)
    
    while True:
        cv2.imshow('image',img)
        button=cv2.waitKey(1)& 0xff
        if button==ord('q'):
            break
        b=cv2.getTrackbarPos('B','trackbar')
        g=cv2.getTrackbarPos('G','trackbar')
        r=cv2.getTrackbarPos('R','trackbar')
        img[:]=[b,g,r]
    cv2.destroyAllWindows()
