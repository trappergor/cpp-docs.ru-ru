---
title: "Класс CD2DBitmap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DBitmap
- CD2DBitmap
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmap class
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f88a6376069c07c61311d74faca104e821a259bd
ms.lasthandoff: 02/24/2017

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
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Деструктор Вызывается при уничтожении объекта D2D точечного рисунка.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Перегружен. Создает объект CD2DBitmap.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DBitmap::Attach](#attach)|Присоединение существующих ресурсов интерфейса в объект|  
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Копирует указанную область в указанном точечном рисунке в текущем растровое изображение|  
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Копирует указанную область памяти в текущей точечного рисунка|  
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Копирует заданную область из указанного целевой объект отрисовки в текущем растровое изображение|  
|[CD2DBitmap::CREATE](#create)|Создает CD2DBitmap. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmap::destroy](#destroy)|Уничтожает объект CD2DBitmap. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBitmap::Detach](#detach)|Отсоединяет интерфейс ресурса из объекта|  
|[CD2DBitmap::Get](#get)|Возвращает интерфейс ID2D1Bitmap|  
|[CD2DBitmap::GetDPI](#getdpi)|Возвращает число точек на дюйм (DPI) растрового изображения|  
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Получает режим формат и альфа-пикселов точечного рисунка|  
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Возвращает размер в единицах, зависящих от устройства (в пикселях), растрового изображения|  
|[CD2DBitmap::GetSize](#getsize)|Возвращает размер в аппаратно независимые пиксели (DIP) растрового изображения|  
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
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Дескриптор точечного рисунка источника.|  
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Тип ресурса.|  
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|Хранит указатель на объект ID2D1Bitmap.|  
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Битовая карта, размер назначения.|  
|[CD2DBitmap::m_strPath](#m_strpath)|Путь к файлу Botmap.|  
|[CD2DBitmap::m_uiResID](#m_uiresid)|Идентификатор ресурса растрового изображения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBitmap`
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dbitmapa--cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2DBitmap:: ~ CD2DBitmap  
 Деструктор Вызывается при уничтожении объекта D2D точечного рисунка.  
  
```  
virtual ~CD2DBitmap();
```  
  
##  <a name="a-nameattacha--cd2dbitmapattach"></a><a name="attach"></a>CD2DBitmap::Attach  
 Присоединение существующих ресурсов интерфейса в объект  
  
```  
void Attach(ID2D1Bitmap* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Существующий интерфейс ресурсов. Не может иметь значение NULL  
  
##  <a name="a-namecd2dbitmapa--cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2DBitmap::CD2DBitmap  
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
 Указатель нулем строка, содержащая тип ресурса.  
  
 `sizeDest`  
 Целевой размер растрового изображения.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
 `lpszPath`  
 Указатель нулем строка, содержащая имя файла.  
  
 `hbmpSrc`  
 Дескриптор точечного рисунка.  
  
##  <a name="a-namecommoninita--cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2DBitmap::CommonInit  
 Инициализирует объект  
  
```  
void CommonInit();
```  
  
##  <a name="a-namecopyfrombitmapa--cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>CD2DBitmap::CopyFromBitmap  
 Копирует указанную область в указанном точечном рисунке в текущем растровое изображение  
  
```  
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Для копирования из растрового изображения  
  
 `destPoint`  
 В текущем точечного рисунка копируются в левый верхний угол области, к которому области указанной srcRect  
  
 `srcRect`  
 Область растрового изображения для копирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namecopyfrommemorya--cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>CD2DBitmap::CopyFromMemory  
 Копирует указанную область памяти в текущей точечного рисунка  
  
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
 Шаг или шаг исходного растрового изображения, хранящиеся в srcData. Шаг – количество байтов строке пикселей (от одного ряда точек в памяти). Шаг может быть вычислено с помощью следующей формулы: ширина в пикселях * байт на пиксел + заполнение памяти  
  
 `destRect`  
 В текущем точечного рисунка копируются в левый верхний угол области, к которому области указанной srcRect  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namecopyfromrendertargeta--cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>CD2DBitmap::CopyFromRenderTarget  
 Копирует заданную область из указанного целевой объект отрисовки в текущем растровое изображение  
  
```  
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Целевой объект отрисовки, содержащей область для копирования  
  
 `destPoint`  
 В текущем точечного рисунка копируются в левый верхний угол области, к которому области указанной srcRect  
  
 `srcRect`  
 Область renderTarget для копирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namecreatea--cd2dbitmapcreate"></a><a name="create"></a>CD2DBitmap::CREATE  
 Создает CD2DBitmap.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Указатель на целевой объект отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namedestroya--cd2dbitmapdestroy"></a><a name="destroy"></a>CD2DBitmap::destroy  
 Уничтожает объект CD2DBitmap.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dbitmapdetach"></a><a name="detach"></a>CD2DBitmap::Detach  
 Отсоединяет интерфейс ресурса из объекта  
  
```  
ID2D1Bitmap* Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс отсоединенных ресурсов.  
  
##  <a name="a-namegeta--cd2dbitmapget"></a><a name="get"></a>CD2DBitmap::Get  
 Возвращает интерфейс ID2D1Bitmap  
  
```  
ID2D1Bitmap* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Bitmap или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetdpia--cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2DBitmap::GetDPI  
 Возвращает число точек на дюйм (DPI) растрового изображения  
  
```  
CD2DSizeF GetDPI() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Горизонтальное и вертикальное разрешение точечного рисунка.  
  
##  <a name="a-namegetpixelformata--cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2DBitmap::GetPixelFormat  
 Получает режим формат и альфа-пикселов точечного рисунка  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Пиксель формат и альфа-режим растрового изображения.  
  
##  <a name="a-namegetpixelsizea--cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>CD2DBitmap::GetPixelSize  
 Возвращает размер в единицах, зависящих от устройства (в пикселях), растрового изображения  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в пикселях точечного рисунка...  
  
##  <a name="a-namegetsizea--cd2dbitmapgetsize"></a><a name="getsize"></a>CD2DBitmap::GetSize  
 Возвращает размер в аппаратно независимые пиксели (DIP) растрового изображения  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в частные интерфейсы растрового изображения.  
  
##  <a name="a-nameisvalida--cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2DBitmap::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="a-namembautodestroyhbmpa--cd2dbitmapmbautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2DBitmap::m_bAutoDestroyHBMP  
 Значение TRUE, если m_hBmpSrc должно быть уничтожено; в противном случае — значение FALSE.  
  
```  
BOOL m_bAutoDestroyHBMP;  
```  
  
##  <a name="a-namemhbmpsrca--cd2dbitmapmhbmpsrc"></a><a name="m_hbmpsrc"></a>CD2DBitmap::m_hBmpSrc  
 Дескриптор точечного рисунка источника.  
  
```  
HBITMAP m_hBmpSrc;  
```  
  
##  <a name="a-namemlpsztypea--cd2dbitmapmlpsztype"></a><a name="m_lpsztype"></a>CD2DBitmap::m_lpszType  
 Тип ресурса.  
  
```  
LPCTSTR m_lpszType;  
```  
  
##  <a name="a-namempbitmapa--cd2dbitmapmpbitmap"></a><a name="m_pbitmap"></a>CD2DBitmap::m_pBitmap  
 Хранит указатель на объект ID2D1Bitmap.  
  
```  
ID2D1Bitmap* m_pBitmap;  
```  
  
##  <a name="a-namemsizedesta--cd2dbitmapmsizedest"></a><a name="m_sizedest"></a>CD2DBitmap::m_sizeDest  
 Битовая карта, размер назначения.  
  
```  
CD2DSizeU m_sizeDest;  
```  
  
##  <a name="a-namemstrpatha--cd2dbitmapmstrpath"></a><a name="m_strpath"></a>CD2DBitmap::m_strPath  
 Путь к файлу Botmap.  
  
```  
CString m_strPath;  
```  
  
##  <a name="a-namemuiresida--cd2dbitmapmuiresid"></a><a name="m_uiresid"></a>CD2DBitmap::m_uiResID  
 Идентификатор ресурса растрового изображения.  
  
```  
UINT m_uiResID;  
```  
  
##  <a name="a-nameoperatorid2d1bitmapstara--cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2DBitmap::operator ID2D1Bitmap *  
 Возвращает интерфейс ID2D1Bitmap  
  
```  
operator ID2D1Bitmap*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1Bitmap или значение NULL, если объект еще не инициализирован.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

