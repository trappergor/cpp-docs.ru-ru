---
title: "Функции серого цвета и сглаживания точечного рисунка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: b8b6f43917dfe211f477b3dde0c94323015d18b2
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>Функции серого цвета и сглаживания точечного рисунка
**Функции серого точечного рисунка**  
  
 MFC предоставляет две функции для придания растровому изображению вида отключенного элемента управления.  
  
 ![Сравнение версий серых и оригинальных значок](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Рисует серую версию растрового изображения.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Копирует серую версию растрового изображения.|  
  
 **Функции сглаживания точечного рисунка**  
  
 MFC также предоставляет две функции для замены фона растрового изображения сглаженным шаблоном.  
  
 ![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Рисует растровое изображение со сглаженным фоном.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Копирует растровое изображение со сглаженным фоном.|  
  
##  <a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap  
 Рисует серую версию растрового изображения.  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указывает на целевой контекст устройства.  
  
 *x*  
 Целевая координата по оси x.  
  
 *y*  
 Целевая координата по оси y.  
  
 `rSrc`  
 Исходное растровое изображение.  
  
 `crBackground`  
 Новый цвет фона (обычно серый, например в случае с COLOR_MENU).  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение, рисуемое с использованием `AfxDrawGrayBitmap` , будет выглядеть как отключенный элемент управления.  
  
 ![Сравнение версий серых и оригинальных значок](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#191;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>AfxGetGrayBitmap  
 Копирует серую версию растрового изображения.  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Исходное растровое изображение.  
  
 `pDest`  
 Растровое изображение назначения.  
  
 `crBackground`  
 Новый цвет фона (обычно серый, например в случае с COLOR_MENU).  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение, копируемое с использованием `AfxGetGrayBitmap` , будет выглядеть как отключенный элемент управления.  
  
 ![Сравнение версий серых и оригинальных значок](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#193;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap  
 Рисуется растровое изображение, заменив его фона узора сглаживания (проверка).  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указывает на целевой контекст устройства.  
  
 *x*  
 Целевая координата по оси x.  
  
 *y*  
 Целевая координата по оси y.  
  
 `rSrc`  
 Исходное растровое изображение.  
  
 `cr1`  
 Один из цветов двух сглаживания обычно белых.  
  
 `cr2`  
 Другие сглаживания цвет, обычно светло-серый цвет (COLOR_MENU).  
  
### <a name="remarks"></a>Примечания  
 Исходный точечный рисунок рисуется на конечный контроллер домена с помощью двух цветов ( `cr1` и `cr2`) клетчатого шаблона замены фона растрового изображения. Исходный точечный рисунок фона определяется как его белым и всех пикселей сопоставления цвет пикселя в левом верхнем углу точечного рисунка.  
  
 ![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#190;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap  
 Копирует точечный рисунок, заменив его фона узора сглаживания (проверка).  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Исходное растровое изображение.  
  
 `pDest`  
 Растровое изображение назначения.  
  
 `cr1`  
 Один из цветов двух сглаживания обычно белых.  
  
 `cr2`  
 Другие сглаживания цвет, обычно светло-серый цвет (COLOR_MENU).  
  
### <a name="remarks"></a>Примечания  
 Исходный точечный рисунок копируется в точечный рисунок назначения с помощью двух цветов ( `cr1` и `cr2`) клетчатого шаблона замены исходный точечный рисунок фона. Исходный точечный рисунок фона определяется как его белым и всех пикселей сопоставления цвет пикселя в левом верхнем углу точечного рисунка.  
  
 ![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#192;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

