# officialDemoLoc问题反馈



## 问题一   定位时间比较慢

### 场景一   iPhone 7 Plus  iOS15.4.1需要10秒才出定位结果  iPhone X iOS13.6只需要不到1秒就出定位结果
```objective-c
   //场景一   iPhone 7 Plus  iOS15.4.1需要10秒才出定位结果  iPhone X iOS13.6只需要不到1秒就出定位结果
    //设置期望定位精度
    [self.locationManager setDesiredAccuracy:kCLLocationAccuracyHundredMeters];
    //设置定位超时时间
    [self.locationManager setLocationTimeout:10];
    //设置逆地理超时时间
    [self.locationManager setReGeocodeTimeout:10];
```

### 场景二   iPhone 7 Plus  iOS15.4.1需要10秒才出定位结果  iPhone X iOS13.6需要10秒才出定位结果
```objective-c
    //场景二   iPhone 7 Plus  iOS15.4.1需要10秒才出定位结果  iPhone X iOS13.6需要10秒才出定位结果
    //设置期望定位精度
    [self.locationManager setDesiredAccuracy:kCLLocationAccuracyNearestTenMeters];
    //设置定位超时时间
    [self.locationManager setLocationTimeout:10];
    //设置逆地理超时时间
    [self.locationManager setReGeocodeTimeout:10];
```

### 场景三   iPhone 7 Plus  iOS15.4.1需要10秒才出定位结果  iPhone X iOS13.6需要10秒才出定位结果
**目前项目中需要使用的是场景三，需要最高精度的定位**

```objective-c
//设置期望定位精度
    [self.locationManager setDesiredAccuracy:kCLLocationAccuracyBest];
    //设置定位超时时间
    [self.locationManager setLocationTimeout:10];
    //设置逆地理超时时间
    [self.locationManager setReGeocodeTimeout:10];
```


## 问题二   持续定位和后台持续定位不返回结果

### 持续定位：
1）iPhone 7 Plus  iOS15.4.1 返回3次结果后，移动设备没有持续的返回定位结果
2）iPhone X iOS13.6 会隔几秒持续返回定位结果

```objective-c
- (void)amapLocationManager:(AMapLocationManager *)manager didUpdateLocation:(CLLocation *)location reGeocode:(AMapLocationReGeocode *)reGeocode
{
    //iPhone 7 Plus  iOS15.4.1 返回3次结果后，移动设备没有持续的返回定位结果
    //iPhone X iOS13.6 会隔几秒持续返回定位结果
    NSLog(@"CCCCC location:{lat:%f; lon:%f; accuracy:%f; reGeocode:%@}", location.coordinate.latitude, location.coordinate.longitude, location.horizontalAccuracy, reGeocode.formattedAddress);
}
```

### 后台持续定位：
1）iPhone 7 Plus  iOS15.4.1 返回3次结果后，移动设备没有持续的返回定位结果
2）iPhone X iOS13.6 会隔几秒持续返回定位结果

```objective-c
- (void)amapLocationManager:(AMapLocationManager *)manager didUpdateLocation:(CLLocation *)location reGeocode:(AMapLocationReGeocode *)reGeocode
{
    //iPhone 7 Plus  iOS15.4.1 返回3次结果后，移动设备没有持续的返回定位结果
    //iPhone X iOS13.6 会隔几秒持续返回定位结果
    NSLog(@"CCCC location:{lat:%f; lon:%f; accuracy:%f; reGeocode:%@}", location.coordinate.latitude, location.coordinate.longitude, location.horizontalAccuracy, reGeocode.formattedAddress);
}
```