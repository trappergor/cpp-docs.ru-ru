---
title: "Класс CD2DTextFormat | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
dev_langs: C++
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26fbbbe2d9f5edde6e247d69e9e6bc840f05a55b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dtextformat-class"></a>Класс CD2DTextFormat
Программа-оболочка для IDWriteTextFormat.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Создает объект CD2DTextFormat.|  
|[CD2DTextFormat:: ~ CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|Деструктор Вызывается при уничтожении объекта D2D текстовый формат.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DTextFormat::CREATE](#create)|Создает CD2DTextFormat. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextFormat::destroy](#destroy)|Уничтожает объект CD2DTextFormat. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextFormat::Get](#get)|Возвращает интерфейс IDWriteTextFormat|  
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Возвращает копию имя семейства шрифтов.|  
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Возвращает копию языкового стандарта.|  
|[CD2DTextFormat::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextFormat::ReCreate](#recreate)|Повторно создает CD2DTextFormat. (Переопределяет [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Возвращает интерфейс IDWriteTextFormat|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Указатель на IDWriteTextFormat.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextformat"></a>CD2DTextFormat:: ~ CD2DTextFormat  
 Деструктор Вызывается при уничтожении объекта D2D текстовый формат.  
  
```  
virtual ~CD2DTextFormat();
```  
  
##  <a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat  
 Создает объект CD2DTextFormat.  
  
```  
CD2DTextFormat(
    CRenderTarget* pParentTarget,  
    const CString& strFontFamilyName,  
    FLOAT fontSize,  
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,  
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,  
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,  
    const CString& strFontLocale = _T(""),  
    IDWriteFontCollection* pFontCollection = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentTarget`  
 Указатель на целевой объект отрисовки.  
  
 `strFontFamilyName`  
 Объект CString, содержащая имя семейства шрифтов.  
  
 `fontSize`  
 Логический размер шрифта в единицах DIP («аппаратно независимый пиксель»). DIPequals 1/96 дюйма.  
  
 `fontWeight`  
 Значение, указывающее насыщенность шрифта для текста объекта.  
  
 `fontStyle`  
 Значение, указывающее начертание шрифта для текста объекта.  
  
 `fontStretch`  
 Значение, указывающее растяжения шрифта для текста объекта.  
  
 `strFontLocale`  
 Объект CString, содержащий имя языкового стандарта.  
  
 `pFontCollection`  
 Указатель на объект коллекции шрифтов. Если это значение NULL, указывает коллекции системных шрифтов.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельца (pParentTarget).  
  
##  <a name="create"></a>CD2DTextFormat::CREATE  
 Создает CD2DTextFormat.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="destroy"></a>CD2DTextFormat::destroy  
 Уничтожает объект CD2DTextFormat.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextFormat::Get  
 Возвращает интерфейс IDWriteTextFormat  
  
```  
IDWriteTextFormat* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextFormat или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getfontfamilyname"></a>CD2DTextFormat::GetFontFamilyName  
 Возвращает копию имя семейства шрифтов.  
  
```  
CString GetFontFamilyName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 CString объект, содержащий текущее имя семейства шрифтов.  
  
##  <a name="getlocalename"></a>CD2DTextFormat::GetLocaleName  
 Возвращает копию языкового стандарта.  
  
```  
CString GetLocaleName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 CString объект, содержащий имя текущего языкового стандарта.  
  
##  <a name="isvalid"></a>CD2DTextFormat::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_ptextformat"></a>CD2DTextFormat::m_pTextFormat  
 Указатель на IDWriteTextFormat.  
  
```  
IDWriteTextFormat* m_pTextFormat;  
```  
  
##  <a name="operator_idwritetextformat_star"></a>CD2DTextFormat::operator IDWriteTextFormat *  
 Возвращает интерфейс IDWriteTextFormat  
  
```  
operator IDWriteTextFormat*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextFormat или значение NULL, если объект еще не инициализирован.  
  
##  <a name="recreate"></a>CD2DTextFormat::ReCreate  
 Повторно создает CD2DTextFormat.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
