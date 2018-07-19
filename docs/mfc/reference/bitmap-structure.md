---
title: Структуру ТОЧЕЧНОГО | Документация Майкрософт
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
ms.openlocfilehash: ddc4868d7cc3c094ad2bb81b5d9706a2b749553d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339351"
---
# <a name="bitmap-structure"></a>Структура BITMAP
**Точечного РИСУНКА** структура определяет высоту, ширину, формат цвета и значения битов Битовая карта логических **.**  
  
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
 Указывает тип растрового изображения. Для логического растровых изображений этот элемент должен быть 0.  
  
 *bmWidth*  
 Ширина растрового изображения в пикселях. Ширина должна быть больше 0.  
  
 *bmHeight*  
 Высота растрового изображения в растровой строки. Высота должна быть больше 0.  
  
 *bmWidthBytes*  
 Указывает число байтов в каждой строке растровые. Это значение должно быть четным числом, так как интерфейс графических устройств (GDI) предполагается, что значения битов битовой карты формируют массив значений (2-байтовое) целое число. Другими словами *bmWidthBytes* \* 8 должны быть следующего размера, кратного 16 больше или равно значению, полученный при *bmWidth* умножается на член *bmBitsPixel*  член.  
  
 *bmPlanes*  
 Задается число цветовых плоскостей в битовой карте.  
  
 *bmBitsPixel*  
 Число смежных цветовых битов на каждой плоскости, необходимую для определения точки.  
  
 *bmBits*  
 Указывает на расположение двоичных значений для растрового изображения. *BmBits* член должен быть длинный указатель на массив 1-байтовых значений.  
  
## <a name="remarks"></a>Примечания  
 Используемое в настоящее время точечного рисунка форматы: монохромная и цвет. Монохромный точечный рисунок использует формат бит 1, 1-плоскости. Для каждого сканирования кратно 16 бит.  
  
 Сканирование упорядочены следующим образом для монохромную битовую карту от высоты *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Пиксели на устройстве монохромный являются либо черный или белый. В случае соответствующий бит в битовой карте 1 пикселя включен (белый). Если соответствующий бит в битовой карте равно 0, пикселя будет отключено (черный).  
  
 Все устройства поддерживают точечные рисунки, срок действия набора RC_BITBLT бит в индекс RASTERCAPS [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) функция-член.  
  
 Каждое устройство имеет свой собственный уникальный цвет формат. Чтобы передать точечный рисунок с одного устройства в другую, используйте [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) и [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) функции Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
