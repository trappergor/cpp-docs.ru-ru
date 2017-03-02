---
title: "Структура точечный РИСУНОК | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd7e63cfe9e7a0f2305ca5c3cd7c2571a080a718
ms.lasthandoff: 02/24/2017

---
# <a name="bitmap-structure"></a>Структура BITMAP
**Точечный РИСУНОК** структура определяет высоту, ширину, формат цвета и точечный рисунок логические значения битов**.**  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagBITMAP {  /* bm */  
    int bmType;  
    int bmWidth;  
    int bmHeight;  
    int bmWidthBytes;  
    BYTE bmPlanes;  
    BYTE bmBitsPixel;  
    LPVOID bmBits;  
} BITMAP;  
```  
  
#### <a name="parameters"></a>Параметры  
 *bmType*  
 Указывает тип точечного рисунка. Для логических точечные рисунки этот член должно быть 0.  
  
 *bmWidth*  
 Ширина растрового изображения в пикселях. Ширина должна быть больше 0.  
  
 *bmHeight*  
 Высота растрового изображения в растровые строк. Высота должна быть больше 0.  
  
 *bmWidthBytes*  
 Указывает число байтов в каждой строке растровые. Это значение должно быть четным числом, поскольку интерфейс графических устройств (GDI) предполагает, что значения битов точечного рисунка форме массив (2-байтовые) целые значения. Другими словами **bmWidthBytes** \* 8 должен быть следующего размера, кратного 16 больше или равно значению, полученные при **bmWidth** умножается на член **bmBitsPixel** член.  
  
 *bmPlanes*  
 Задается число цветовых плоскостей в битовой карте.  
  
 *bmBitsPixel*  
 Указывает число битов на смежные цвета на каждой плоскости, необходимые для определения точки.  
  
 *bmBits*  
 Указывает расположение битовые значения для точечного рисунка. **BmBits** элемент должен быть длинный указатель на массив 1-байтовых значений.  
  
## <a name="remarks"></a>Примечания  
 Форматы в настоящее время используется битовая карта, монохромный и цвет. Монохромный точечный рисунок отображается в формате 1-разрядной, плоскость 1. Каждая операция сканирования делится на 16 бит.  
  
 Просмотров упорядочены следующим образом для монохромный точечный рисунок высоты *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Пиксели на устройстве монохромный, либо черный или белый. Если 1, соответствующий бит в битовой карте пикселя включена (белый цвет). Если соответствующий бит в битовой карте равно 0, пикселя будет отключена (черный).  
  
 Все устройства поддерживают точечным рисункам, имеющим **RC_BITBLT** бит установлен в **RASTERCAPS** индекс [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) функции-члена.  
  
 Каждое устройство имеет собственный уникальный цвет формат. Чтобы перенести растрового изображения с одного устройства к другому, используйте [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) и [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) функции Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)

