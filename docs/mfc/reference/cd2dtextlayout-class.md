---
title: "Класс CD2DTextLayout | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 3d1307eb4f747fa06a21d9b2b8fd65dec2defbe5
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dtextlayout-class"></a>Класс CD2DTextLayout
Программа-оболочка для IDWriteTextLayout.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Создает объект CD2DTextLayout.|  
|[CD2DTextLayout:: ~ CD2DTextLayout](#cd2dtextlayout__~cd2dtextlayout)|Деструктор Вызывается при уничтожении объекта D2D текст макета.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextLayout::CREATE](#create)|Создает CD2DTextLayout. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextLayout::destroy](#destroy)|Уничтожает объект CD2DTextLayout. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextLayout::Get](#get)|Возвращает интерфейс IDWriteTextLayout|  
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Копирует имя семейства шрифтов текста в указанной позиции.|  
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Возвращает имя языкового стандарта текста в указанной позиции.|  
|[CD2DTextLayout::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextLayout::ReCreate](#recreate)|Повторно создает CD2DTextLayout. (Переопределяет [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Имя семейства шрифтов, заканчивающаяся наборов для текста в пределах указанного текстового диапазона|  
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Задает имя языкового стандарта для текста в диапазон указанного текста|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextLayout::operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|Возвращает интерфейс IDWriteTextLayout|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Указатель на IDWriteTextLayout.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextlayout"></a>CD2DTextLayout:: ~ CD2DTextLayout  
 Деструктор Вызывается при уничтожении объекта D2D текст макета.  
  
```  
virtual ~CD2DTextLayout();
```  
  
##  <a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout  
 Создает объект CD2DTextLayout.  
  
```  
CD2DTextLayout(
    CRenderTarget* pParentTarget,  
    const CString& strText,  
    CD2DTextFormat& textFormat,  
    const CD2DSizeF& sizeMax,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `strText`  
 Объект CString, содержащий строку, чтобы создать новый объект CD2DTextLayout из.  
  
 `textFormat`  
 Объект CString, содержащий формат, применяемый к строке.  
  
 `sizeMax`  
 Размер окна макета.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="create"></a>CD2DTextLayout::CREATE  
 Создает CD2DTextLayout.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DTextLayout::destroy  
 Уничтожает объект CD2DTextLayout.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextLayout::Get  
 Возвращает интерфейс IDWriteTextLayout  
  
```  
IDWriteTextLayout* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextLayout или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName  
 Копирует имя семейства шрифтов текста в указанной позиции.  
  
```  
CString GetFontFamilyName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `currentPosition`  
 Положение текста для проверки.  
  
 `textRange`  
 Диапазон текста, который имеет те же отформатировать как текст в позиции, указанной параметром currentPosition. Это означает, что выполнение имеет точный как заданная позиция, включая, но не ограничиваясь имя семейства шрифтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 CString объект, содержащий текущее имя семейства шрифтов.  
  
##  <a name="getlocalename"></a>CD2DTextLayout::GetLocaleName  
 Возвращает имя языкового стандарта текста в указанной позиции.  
  
```  
CString GetLocaleName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `currentPosition`  
 Положение текста для проверки.  
  
 `textRange`  
 Диапазон текста, который имеет те же отформатировать как текст в позиции, указанной параметром currentPosition. Это означает, что выполнение имеет точный как заданная позиция, включая, но не ограничиваясь имени языкового стандарта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 CString объект, содержащий имя текущего языкового стандарта.  
  
##  <a name="isvalid"></a>CD2DTextLayout::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout  
 Указатель на IDWriteTextLayout.  
  
```  
IDWriteTextLayout* m_pTextLayout;  
```  
  
##  <a name="operator_idwritetextlayout_star"></a>CD2DTextLayout::operator IDWriteTextLayout *  
 Возвращает интерфейс IDWriteTextLayout  
  
```  
operator IDWriteTextLayout*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextLayout или значение NULL, если объект еще не инициализирован.  
  
##  <a name="recreate"></a>CD2DTextLayout::ReCreate  
 Повторно создает CD2DTextLayout.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName  
 Имя семейства шрифтов, заканчивающаяся наборов для текста в пределах указанного текстового диапазона  
  
```  
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Параметры  
 `pwzFontFamilyName`  
 Имя семейства шрифтов, который применяется к всей строки текста в диапазоне, определяемом textRange  
  
 `textRange`  
 Текстовый диапазон, к которому применяется данное изменение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE  
  
##  <a name="setlocalename"></a>CD2DTextLayout::SetLocaleName  
 Задает имя языкового стандарта для текста в диапазон указанного текста  
  
```  
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Параметры  
 `pwzLocaleName`  
 Строка имени языкового стандарта символом null  
  
 `textRange`  
 Текстовый диапазон, к которому применяется данное изменение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

