---
layout: page
title: Competitive Programming
comments: false
---


{% highlight python linenos %}
carmodel = cv2.CascadeClassifier('haar_mode.xml')

# car detection using pre trained Haar Cascades
# model using OpenCV
def detect_cars(image):
    image = cv2.resize(image, (WIDTH, HEIGHT))
    gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    cars = carmodel.detectMultiScale(gray,1.1,13,18,(24,24))
    return cars

# speed estimation using pixel difference
# between 2 frames
def get_speed(loc1, loc2, f1, f2):
    # get pixel distances of the same car
    d_pixels = sqrt(pow(loc2[0] - loc1[0], 2)
                    + pow(loc2[1] - loc1[1], 2))
    # convert pixel distance to real world distance
    # feet per pixel is a pre-calibrated ratio
    d = d_pixels * FEET_PER_PIXEL * FEET_TO_MILE
    # get seconds elapsed from frame1 to frame2
    t = (f2 - f1) / FRAMES_PER_SECOND
    s = d / t * 3600
    return s


# check current car against all cars in active car list
# and check if there's a match
def track_car(curr_car, active_car_list):
    x, y, w, h = curr_car
    x_bar = x + 0.5 * w
    y_bar = y + 0.5 * h

    matched_car_id = -1
    for i in active_car_list.keys():
        t_x, t_y, t_w, t_h = active_car_list[i]

        t_x_bar = t_x + 0.5 * t_w
        t_y_bar = t_y + 0.5 * t_h

        if ((t_x <= x_bar <= (t_x + t_w))
                and (t_y <= y_bar <= (t_y + t_h))
                and (x <= t_x_bar <= (x + w))
                and (y <= t_y_bar <= (y + h))):
            matched_car_id = i

        return matched_car_id

{% endhighlight %}
