---
title: "Класс CD2DTextFormat | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DTextFormat
- CD2DTextFormat
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextFormat class
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: 16
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
ms.openlocfilehash: 5f7347dbbad8290bfdc800cbacaf21400583a392
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dtextformat-class"></a>Класс CD2DTextFormat
Программа-оболочка для IDWriteTextFormat.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Создает объект CD2DTextFormat.|  
|[CD2DTextFormat:: ~ CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|Деструктор Вызывается при уничтожении объекта D2D текстовый формат.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextFormat::CREATE](#create)|Создает CD2DTextFormat. (Переопределяет [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextFormat::destroy](#destroy)|Уничтожает объект CD2DTextFormat. (Переопределяет [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextFormat::Get](#get)|Возвращает интерфейс IDWriteTextFormat|  
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Возвращает копию имя семейства шрифтов.|  
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Возвращает копию имени языкового стандарта.|  
|[CD2DTextFormat::IsValid](#isvalid)|Проверяет допустимость ресурсов (переопределяет [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextFormat::ReCreate](#recreate)|Повторно создает CD2DTextFormat. (Переопределяет [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Возвращает интерфейс IDWriteTextFormat|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Указатель на IDWriteTextFormat.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dtextformata--cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2DTextFormat:: ~ CD2DTextFormat  
 Деструктор Вызывается при уничтожении объекта D2D текстовый формат.  
  
```  
virtual ~CD2DTextFormat();
```  
  
##  <a name="a-namecd2dtextformata--cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat  
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
 Значение, указывающее, насыщенность шрифта для текста объекта.  
  
 `fontStyle`  
 Значение, указывающее стиль шрифта для текстового объекта.  
  
 `fontStretch`  
 Значение, указывающее растяжение шрифта для текста объекта.  
  
 `strFontLocale`  
 Объект CString, содержащий имя языкового стандарта.  
  
 `pFontCollection`  
 Указатель на объект семейства шрифтов. Если это значение NULL, указывает коллекции системных шрифтов.  
  
 `bAutoDestroy`  
 Указывает, что объект будет уничтожен владельцем (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dtextformatcreate"></a><a name="create"></a>CD2DTextFormat::CREATE  
 Создает CD2DTextFormat.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="a-namedestroya--cd2dtextformatdestroy"></a><a name="destroy"></a>CD2DTextFormat::destroy  
 Уничтожает объект CD2DTextFormat.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namegeta--cd2dtextformatget"></a><a name="get"></a>CD2DTextFormat::Get  
 Возвращает интерфейс IDWriteTextFormat  
  
```  
IDWriteTextFormat* Get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextFormat или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namegetfontfamilynamea--cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextFormat::GetFontFamilyName  
 Возвращает копию имя семейства шрифтов.  
  
```  
CString GetFontFamilyName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект CString, содержащий текущее имя семейства шрифтов.  
  
##  <a name="a-namegetlocalenamea--cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>CD2DTextFormat::GetLocaleName  
 Возвращает копию имени языкового стандарта.  
  
```  
CString GetLocaleName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект CString, содержащий имя текущего языкового стандарта.  
  
##  <a name="a-nameisvalida--cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2DTextFormat::IsValid  
 Проверяет допустимость ресурсов  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="a-namemptextformata--cd2dtextformatmptextformat"></a><a name="m_ptextformat"></a>CD2DTextFormat::m_pTextFormat  
 Указатель на IDWriteTextFormat.  
  
```  
IDWriteTextFormat* m_pTextFormat;  
```  
  
##  <a name="a-nameoperatoridwritetextformatstara--cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>CD2DTextFormat::operator IDWriteTextFormat *  
 Возвращает интерфейс IDWriteTextFormat  
  
```  
operator IDWriteTextFormat*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IDWriteTextFormat или значение NULL, если объект еще не инициализирован.  
  
##  <a name="a-namerecreatea--cd2dtextformatrecreate"></a><a name="recreate"></a>CD2DTextFormat::ReCreate  
 Повторно создает CD2DTextFormat.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

