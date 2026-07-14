# Cheating Surveillance System

Hệ thống giám sát gian lận trong **Online Interviews/Exams** bằng cách:
- Nhận diện hướng nhìn (gaze) từ **dlib 68 landmarks**
- Ước lượng hướng đầu từ **solvePnP**
- Phát hiện **điện thoại** bằng **YOLO (best_yolov12.pt)**

## Cấu trúc thư mục
```
.
├─ main.py
├─ eye_movement.py
├─ head_pose.py
├─ mobile_detection.py
├─ model/
│  ├─ best_yolov12.pt
│  ├─ best_yolov8.pt   (có sẵn)
│  └─ shape_predictor_68_face_landmarks.dat
├─ Demo_vid/
│  ├─ gaze-detection.mp4
│  ├─ headpose-detection.mp4
│  └─ Mobile-detection.mp4
├─ log/               (ảnh chụp cảnh báo)
└─ requirements.txt
```

## Cài đặt nhanh
```bash
pip install -r requirements.txt
```

> Lưu ý: repo của bạn đã có sẵn model trong thư mục `model/`. Hãy đảm bảo file tồn tại:
> - `model/shape_predictor_68_face_landmarks.dat`
> - `model/best_yolov12.pt`

## Chạy chương trình
```bash
python main.py
```
- Hệ thống mở webcam (index `0`).
- Nhấn **q** để thoát.
- Khi phát hiện lệch head/eye hoặc có điện thoại trong ~3 giây, chương trình sẽ lưu ảnh vào thư mục `log/`.

## Demo
- Gaze detection: `Demo_vid/gaze-detection.mp4`
- Head pose detection: `Demo_vid/headpose-detection.mp4`
- Mobile detection: `Demo_vid/Mobile-detection.mp4`

## Dataset (YOLO)
Model điện thoại được train từ dataset **Roboflow Cellphone Detection**.

## Acknowledgements
- dlib, OpenCV
- Ultralytics YOLO
- Roboflow

