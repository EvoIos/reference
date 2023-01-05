---
title: Objective-C
date: 2022-11-18 19:50:01
icon: icon-java
background: bg-[#d33731]
tags:
    - object-oriented
    - class
categories:
    - Programming
intro: |
    This cheat sheet is a crash course for Java beginners and help review the basic syntax of the Java language.
plugins:
    - tooltip
---


String 相关 {.cols-3}
--------

### NSAttributedStringKey {.row-span-2}
| Type                  | described value        | 
|-----------------------|------------------------|
| `NSFontAttributeName`            | font size   |
| `NSForegroundColorAttributeName` | font color  |
{.show-header}

常用的就这些，字体和颜色


### NSMutableAttributedString
```objc
NSString *text = @"abcdefg...abcdefg";
NSString *highlightedText = @"...";

NSMutableAttributedString *attributedString =
[NSMutableAttributedString alloc] initWithString:text 
                                      attributes:@{
                                        NSForegroundColorAttributeName:[UIColor blackColor], 
                                        NSFontAttributeName:FONTO(14)
                                      }];
// 找到range
NSRange range = [text rangeOfString:highlightedText];
// 判空
if (range.location != NSNotFound) {
  // 给range...加高亮颜色
  [attributedString setAttributes:@{
    NSForegroundColorAttributeName:[UIColor redColor]
  } 
range:range];
}
```

### 计算长度
```objc
[<#title#> boundingRectWithSize:CGSizeMake(SCREEN_WIDTH - 2*k_LeftOffset - 14 - 5, CGFLOAT_MAX) 
    options:NSStringDrawingUsesLineFragmentOrigin 
    attributes:@{NSFontAttributeName:FONTO(12.0)} context:nil].size.height;
```

### attributedString添加下划线
```objc
NSMutableAttributedString *str = [[NSMutableAttributedString alloc] initWithString:TBResourcesLocalizedString(@"mobile_ios_common_order_history_1", nil)];
NSRange strRange = {0,[str length]};
[str addAttribute:NSUnderlineStyleAttributeName value:[NSNumber numberWithInteger:NSUnderlineStyleSingle] range:strRange];
[str addAttributes:@{NSFontAttributeName: FONTO(14)} range:strRange];
[historyBtn setAttributedTitle:str forState:UIControlStateNormal];
```


### button添加touchArea
```objc
[<#buton#> setTouchArea:UIEdgeInsetsMake(10, 30, 10, 10)];

```








