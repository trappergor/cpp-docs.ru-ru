---
title: "Класс COleConvertDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog class
- OLE Convert dialog box
- dialog boxes, OLE
- OLE dialog boxes, Convert
- Convert dialog box
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
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
ms.openlocfilehash: 6db5caf443e7f71c58e2c65b46794c2c9d246d38
ms.lasthandoff: 02/24/2017

---
# <a name="coleconvertdialog-class"></a>Класс COleConvertDialog
Дополнительные сведения см. в разделе [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Создает объект `COleConvertDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|Выполняет преобразование, указанное в диалоговом окне.|  
|[COleConvertDialog::DoModal](#domodal)|Отображение диалогового окна OLE изменение элемента.|  
|[COleConvertDialog::GetClassID](#getclassid)|Возвращает **CLSID** связанный с выбранным элементом.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Указывает, следует ли для рисования элемента в виде значка.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанные со значками форме этого элемента.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Возвращает тип выбранного фрагмента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|Структура, которая управляет поведением диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
 Создает только `COleConvertDialog` объекта.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает элемент, чтобы преобразовывать или активации.  
  
 `dwFlags`  
 Создание флаг, который содержит любое количество следующие значения, объединенные с помощью побитового- or -оператор:  
  
- **CF_SELECTCONVERTTO** указывает, преобразовать в переключатель выберет изначально при вызове диалоговое окно. Это значение по умолчанию.  
  
- **CF_SELECTACTIVATEAS** указывает, что переключатель «активировать» выбирается изначально при вызове диалоговое окно.  
  
- **CF_SETCONVERTDEFAULT** указывает, что класс которого **CLSID** определяется **clsidConvertDefault** членом `m_cv` структуры будет использоваться в качестве шаблона по умолчанию в поле список классов, при выборе переключателя преобразовать в.  
  
- **CF_SETACTIVATEDEFAULT** указывает, что класс которого **CLSID** определяется **clsidActivateDefault** членом `m_cv` структуры будет использоваться в качестве шаблона по умолчанию в поле список классов, выбрав переключатель «активировать».  
  
- **CF_SHOWHELPBUTTON** задает отображение кнопки справки при вызове диалоговое окно.  
  
 `pClassID`  
 Указывает идентификатор CLSID элемента должен быть преобразован или активации. Если **NULL**, **CLSID** связанных с `pItem` будет использоваться.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) и [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) структуры.  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 Эта функция вызывается после успешного возврата из [DoModal](#domodal), либо для преобразования или активировать объект типа [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает элемент, чтобы преобразовывать или активации. Не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Преобразовать или активации в соответствии с информацией, выбранный пользователем в диалоговом окне Преобразовать элемента.  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна преобразования OLE.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_cv](#m_cv) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 Эта функция вызывается для получения **CLSID** связанный с элементом, выбранного в диалоговом окне Преобразовать пользователя.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CLSID** связанный с элементом, который был выбран в диалоговом окне Convert.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 Эта функция вызывается для определения, будет ли пользователю выбрать для отображения выбранного элемента в виде значка.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод, необходимых для визуализации объекта.  
  
- `DVASPECT_CONTENT`Возвращается, если не был установлен флажок виде значка.  
  
- `DVASPECT_ICON`Возвращается, если был установлен флажок виде значка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения о рисовании аспект см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры данных в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 Эта функция вызывается для получения дескриптора метафайла, содержит символическое аспектом выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий значками аспектом выбранного элемента, если флажок виде значка был установлен после закрытия диалогового окна, выбрав **ОК**; в противном случае **NULL**.  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 Эта функция вызывается для определения типа преобразования, выбранного в диалоговом окне Convert.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора, сделанного.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый тип значений определяется **выбора** перечисления тип, объявленный в `COleConvertDialog` класса.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 Выполните краткое описание каждого из этих значений.  
  
- **COleConvertDialog::noConversion** возвращаются, если диалоговое окно было отменено или преобразование не выбрал пользователь. Если `COleConvertDialog::DoModal` возвращается **IDOK**, возможно, что пользователь выбрал другой значок не был выбран.  
  
- **COleConvertDialog::convertItem** возвращается, если установлен переключатель преобразования, пользователь выбирает другой элемент для преобразования, и `DoModal` возвращается **IDOK**.  
  
- **COleConvertDialog::activateAs** возвращается, если был выбран переключатель «активировать», пользователь выбирает другой элемент для активации, и `DoModal` возвращается **IDOK**.  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 Структура типа **OLEUICONVERT** используется для управления поведением диалогового окна «Convert».  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно изменить члены этой структуры, либо непосредственно, либо с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

