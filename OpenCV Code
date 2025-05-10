import cv2
import cvzone.SerialModule
from cvzone.HandTrackingModule import HandDetector

cap = cv2.VideoCapture(0)
detector = HandDetector(detectionCon=1, maxHands=1)
mySerial = cvzone.SerialModule.SerialObject("COM5",9600)
while True:
    success, img = cap.read()
    hands, img = detector.findHands(img)# with image

    #hands = detector.findHans(img)
    #print(len(hands)) //// to see hands without image

    # hands here is a list so no need for writing separate code for pos hand
    if hands:
        hand1 = hands[0]
        lmList1 = hand1["lmList"] #this list contains all 21 differnt landmarks of the finger also flip and find left  and right hand re accurate
        bbox1 = hand1["bbox"]
        centerPoint1 = hand1["center"]#center of the hand cx,cy
        handType1 = hand1["type"]#l or r
        fingers1 = detector.fingersUp(hand1)
        #fprint(fingers1)
        mySerial.sendData(fingers1)


        #if len(hands)== 2:
            #hand2 = hands[1]
            #lmList2 = hand2["lmList"]  # this list contains all 21 differnt landmarks of the finger also flip and find left  and right hand re accurate
            #bbox2 = hand2["bbox"]
            #centerPoint2 = hand2["center"]  # center of the hand cx,cy
            #handType2 = hand2["type"]  # l or r
            #fingers2 = detector.fingersUp(hand2)

            #length, info, img = detector.findDistance(centerPoint1,centerPoint2, img)

            #to find the center point of the object
        #print(bbox1) x,y,width,height

    cv2.imshow("Image", img)
    cv2.waitKey(1)

    #while true part is access camera in python
