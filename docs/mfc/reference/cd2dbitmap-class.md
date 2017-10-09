---
title: "Класс CD2DBitmap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 97d176524d0c4748cd257415264fb05a5c6f1be3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dbitmap-class"></a>Класс CD2DBitmap
Программа-оболочка для ID2D1Bitmap.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Перегружен. Создает объект CD2DBitmap из HBITMAP.|  
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Деструктор Вызывается при уничтожении объекта D2D растрового изображения.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Перегружен. Создает объект CD2DBitmap.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::Attach](#attach)|Присоединяет существующий ресурс интерфейс для объекта|  
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Копирует указанную область в указанном точечном рисунке в текущую битовую карту|  
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Копирует указанную область памяти в текущую битовую карту|  
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Копирует указанную область из указанного целевым объектом прорисовки в текущем растровое изображение|  
|[CD2DBitmap::CREATE](#create)|Создает CD2DBitmap. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmap::destroy](#destroy)|Уничтожает объект CD2DBitmap. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBitmap::Detach](#detach)|Отсоединяет интерфейса ресурсов из объекта|  
|[CD2DBitmap::Get](#get)|Возвращает интерфейс ID2D1Bitmap|  
|[CD2DBitmap::GetDPI](#getdpi)|Возвращает размер в точках на дюйм (DPI) растрового изображения|  
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Возвращает режим формат и альфа-пикселей растрового изображения|  
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Возвращает размер в единицах, зависящие от устройства (в пикселях), растрового изображения|  
|[CD2DBitmap::GetSize](#getsize)|Возвращает размер в аппаратно независимых пикселях (DIP) растрового изображения|  
|[CD2DBitmap::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::CommonInit](#commoninit)|Инициализирует объект|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|Возвращает интерфейс ID2D1Bitmap|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|Значение TRUE, если m_hBmpSrc должно быть уничтожено; в противном случае — значение FALSE.|  
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Дескриптор исходного растрового изображения.|  
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Тип ресурса.|  
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|Хранит указатель на объект ID2D1Bitmap.|  
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Битовая карта, размер назначения.|  
|[CD2DBitmap::m_strPath](#m_strpath)|Путь к файлу Botmap.|  
|[CD2DBitmap::m_uiResID](#m_uiresid)|Идентификатор ресурса точечного рисунка.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBitmap`
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbitmap"></a>CD2DBitmap:: ~ CD2DBitmap  
 Деструктор Вызывается при уничтожении объекта D2D растрового изображения.  
  
```  
virtual ~CD2DBitmap();
```  
  
##  <a name="attach"></a>CD2DBitmap::Attach  
 Присоединяет существующий ресурс интерфейс для объекта  
  
```  
void Attach(ID2D1Bitmap* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Интерфейс существующего ресурса. Не может иметь значение NULL  
  
##  <a name="cd2dbitmap"></a>CD2DBitmap::CD2DBitmap  
 Создает объект CD2DBitmap из ресурса.  
  
```  
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszPath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    HBITMAP hbmpSrc,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `uiResID`  
 Идентификационный номер ресурса ресурса.  
  
 `lpszType`  
 Указатель null нулевым байтом строка, содержащая тип ресурса.  
  
 `sizeDest`  
 Целевой размер растрового изображения.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
 `lpszPath`  
 Указатель на завершающуюся значением null строка, содержащая имя файла.  
  
 `hbmpSrc`  
 Дескриптор растрового изображения.  
  
##  <a name="commoninit"></a>CD2DBitmap::CommonInit  
 Инициализирует объект  
  
```  
void CommonInit();
```  
  
##  <a name="copyfrombitmap"></a>CD2DBitmap::CopyFromBitmap  
 Копирует указанную область в указанном точечном рисунке в текущую битовую карту  
  
```  
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Битовая карта для копирования из  
  
 `destPoint`  
 В текущую битовую карту копируется в верхний левый угол области, к которому области указанной srcRect  
  
 `srcRect`  
 Область растрового изображения для копирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="copyfrommemory"></a>CD2DBitmap::CopyFromMemory  
 Копирует указанную область памяти в текущую битовую карту  
  
```  
HRESULT CopyFromMemory(
    const void* srcData,  
    UINT32 pitch,  
    const CD2DRectU* destRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `srcData`  
 Данные для копирования  
  
 `pitch`  
 Полный шаг или шаг исходного растрового изображения, хранящиеся в srcData. Шаг является количество байтов строке пикселей (по одной строке пикселей в памяти). Шаг можно вычислить по следующей формуле: ширина в пикселях * байт на пиксель + заполнение памяти  
  
 `destRect`  
 В текущую битовую карту копируется в верхний левый угол области, к которому области указанной srcRect  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="copyfromrendertarget"></a>CD2DBitmap::CopyFromRenderTarget  
 Копирует указанную область из указанного целевым объектом прорисовки в текущем растровое изображение  
  
```  
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Целевой объект отрисовки, содержащего область для копирования  
  
 `destPoint`  
 В текущую битовую карту копируется в верхний левый угол области, к которому области указанной srcRect  
  
 `srcRect`  
 Область renderTarget для копирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="create"></a>CD2DBitmap::CREATE  
 Создает CD2DBitmap.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DBitmap::destroy  
 Уничтожает объект CD2DBitmap.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmap::Detach  
 Отсоединяет интерфейса ресурсов из объекта  
  
```  
ID2D1Bitmap* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="get"></a>CD2DBitmap::Get  
 Возвращает интерфейс ID2D1Bitmap  
  
```  
ID2D1Bitmap* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Bitmap или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getdpi"></a>CD2DBitmap::GetDPI  
 Возвращает размер в точках на дюйм (DPI) растрового изображения  
  
```  
CD2DSizeF GetDPI() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальные и вертикальные точек на ДЮЙМ растрового изображения.  
  
##  <a name="getpixelformat"></a>CD2DBitmap::GetPixelFormat  
 Возвращает режим формат и альфа-пикселей растрового изображения  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Пиксель формат и альфа-режим растрового изображения.  
  
##  <a name="getpixelsize"></a>CD2DBitmap::GetPixelSize  
 Возвращает размер в единицах, зависящие от устройства (в пикселях), растрового изображения  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в пикселях растрового изображения...  
  
##  <a name="getsize"></a>CD2DBitmap::GetSize  
 Возвращает размер в аппаратно независимых пикселях (DIP) растрового изображения  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в частные интерфейсы растрового изображения.  
  
##  <a name="isvalid"></a>CD2DBitmap::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_bautodestroyhbmp"></a>CD2DBitmap::m_bAutoDestroyHBMP  
 Значение TRUE, если m_hBmpSrc должно быть уничтожено; в противном случае — значение FALSE.  
  
```  
BOOL m_bAutoDestroyHBMP;  
```  
  
##  <a name="m_hbmpsrc"></a>CD2DBitmap::m_hBmpSrc  
 Дескриптор исходного растрового изображения.  
  
```  
HBITMAP m_hBmpSrc;  
```  
  
##  <a name="m_lpsztype"></a>CD2DBitmap::m_lpszType  
 Тип ресурса.  
  
```  
LPCTSTR m_lpszType;  
```  
  
##  <a name="m_pbitmap"></a>CD2DBitmap::m_pBitmap  
 Хранит указатель на объект ID2D1Bitmap.  
  
```  
ID2D1Bitmap* m_pBitmap;  
```  
  
##  <a name="m_sizedest"></a>CD2DBitmap::m_sizeDest  
 Битовая карта, размер назначения.  
  
```  
CD2DSizeU m_sizeDest;  
```  
  
##  <a name="m_strpath"></a>CD2DBitmap::m_strPath  
 Путь к файлу Botmap.  
  
```  
CString m_strPath;  
```  
  
##  <a name="m_uiresid"></a>CD2DBitmap::m_uiResID  
 Идентификатор ресурса точечного рисунка.  
  
```  
UINT m_uiResID;  
```  
  
##  <a name="operator_id2d1bitmap_star"></a>CD2DBitmap::operator ID2D1Bitmap *  
 Возвращает интерфейс ID2D1Bitmap  
  
```  
operator ID2D1Bitmap*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Bitmap или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

