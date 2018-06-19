---
title: Структура точечный РИСУНОК | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure [MFC]
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa8bb4ab914b4e05eb21cfc45a243328d32bb6d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351641"
---
# <a name="bitmap-structure"></a>Структура BITMAP
**Растрового ИЗОБРАЖЕНИЯ** структура определяет высоту, ширину, цветовой формат и значения битов логических растровое изображение **.**  
  
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
 Указывает тип растрового изображения. Для логических растровых изображений этот элемент должен быть 0.  
  
 *bmWidth*  
 Ширина растрового изображения в пикселях. Ширина должна быть больше 0.  
  
 *bmHeight*  
 Высота растрового изображения в растровых строк. Высота должна быть больше 0.  
  
 *bmWidthBytes*  
 Указывает число байтов в каждой строке растровых. Это значение должно быть четным числом поскольку интерфейс графических устройств (GDI) предполагает, что значения битов растрового изображения образуют массив значений (2-байтовое) целое число со знаком. Другими словами **bmWidthBytes** \* 8 должно быть далее кратно 16 больше или равно значению, полученному при **bmWidth** умножается на член **bmBitsPixel**  член.  
  
 *bmPlanes*  
 Задается число цветовых плоскостей в битовой карте.  
  
 *bmBitsPixel*  
 Указывает количество смежных цветовых битов на каждой плоскости, необходимые для определения точки.  
  
 *bmBits*  
 Указывает на расположение двоичных значений для битовой карты. **BmBits** элемент должен быть длинный указатель на массив 1-байтовых значений.  
  
## <a name="remarks"></a>Примечания  
 Форматы используемой в настоящий момент точечный рисунок: монохромный и цвет. Монохромный точечный рисунок отображается в формате бит 1, 1-плоскости. Каждая операция сканирования делится на 16 бит.  
  
 Просмотров упорядочены следующим образом для монохромный точечный рисунок высоты *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Пикселей на монохромный устройства являются либо черный или белый. Если 1, соответствующий бит в битовой карте пикселя включен (белый цвет). Если соответствующий бит в битовой карте равен 0, точки отключен (черный).  
  
 Все устройства поддерживают растровых изображений, имеющих **RC_BITBLT** бит установлен в **RASTERCAPS** индекс [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) функции-члена.  
  
 Каждое устройство имеет свой собственный уникальный цвет формат. Чтобы перенести растровое изображение с одного устройства к другому, используйте [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) и [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) функции Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
