---
title: "Класс COlePasteSpecialDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
dev_langs:
- C++
helpviewer_keywords:
- Paste Special dialog box
- dialog boxes, Paste Special
- OLE Paste Special dialog box
- COlePasteSpecialDialog class
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
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
ms.openlocfilehash: 6984d714248815b062c564c7eed5c315990855af
ms.lasthandoff: 02/24/2017

---
# <a name="colepastespecialdialog-class"></a>Класс COlePasteSpecialDialog
Используется для диалогового окна OLE "Вставить специальный объект".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Создает объект `COlePasteSpecialDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Добавляет пользовательские форматы список форматов, которые можно вставить в приложение.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Добавляет новую запись в список поддерживаемых форматов буфера обмена.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Добавляет **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`и при необходимости `CF_LINKSOURCE` список форматов можно вставить приложения.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Создает элемент в документе-контейнере, используя указанный формат.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Отображает диалоговое окно OLE Специальная вставка.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Сообщает ли для рисования элемента в виде значка или нет.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанные со значками форме этого элемента.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Возвращает индекс параметры вставки доступны, выбранного пользователем.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Возвращает тип выбранного фрагмента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Структура типа **OLEUIPASTESPECIAL** , управляющий функция диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COlePasteSpecialDialog` при необходимо вызвать это диалоговое окно предназначено. После `COlePasteSpecialDialog` объект был создан, можно использовать [AddFormat](#addformat) и [AddStandardFormats](#addstandardformats) функции-члены для добавления форматы буфера обмена в диалоговое окно. Можно также использовать [m_ps](#m_ps) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ps` Структуры имеет тип **OLEUIPASTESPECIAL**.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="a-nameaddformata--colepastespecialdialogaddformat"></a><a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 Эта функция вызывается для добавления новых форматов в список форматов, которые приложение может поддерживать в Специальная вставка операции.  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>Параметры  
 *FMT*  
 Ссылка на тип данных для добавления.  
  
 `lpszFormat`  
 Строка, описывающая формат для пользователя.  
  
 *lpszResult*  
 Строка, описывающая результат, если выбран этот формат, в диалоговом окне.  
  
 `flags`  
 Различные параметры связывания и внедрения для данного формата. Этот флаг является Побитовая комбинация одного или нескольких различных значений в **OLEUIPASTEFLAG** перечисляемый тип.  
  
 `cf`  
 Используемый формат буфера обмена.  
  
 *Тип носителя задан неверно*  
 Типы мультимедиа, доступные в этом формате. Побитовая комбинация одного или нескольких значений в **TYMED** перечисляемый тип.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат. Эта строка имеет две отдельные строки, разделенной символом «\n». Первая строка соответствует значению, который будет передан в *lpstrFormat* параметра, а второй является таким же, как *lpstrResult* параметр.  
  
 *bEnableIcon*  
 Флаг, указывающий, включен ли флажок виде значка при выборе этот формат в поле со списком.  
  
 *мерцания*  
 Флаг, указывающий, включен ли переключатель «связать» при выборе этот формат в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно вызывать для добавления либо стандартные форматы, такие как **CF_TEXT** или **CF_TIFF** или пользовательских форматов, зарегистрированных в системе приложения. Дополнительные сведения о вставке объектов данных в приложении см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) типа перечисления и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) перечислимый тип в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaddlinkentrya--colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 Добавляет новую запись в список поддерживаемых форматов буфера обмена.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 Используемый формат буфера обмена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) структуру, содержащую сведения для новой записи ссылки.  
  
##  <a name="a-nameaddstandardformatsa--colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 Вызовите эту функцию, чтобы добавить следующие форматы буфера обмена в список форматов, которые приложение может поддерживать в Специальная вставка операции:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableLink*  
 Флаг, указывающий, следует ли добавить `CF_LINKSOURCE` список форматов можно вставить приложения.  
  
### <a name="remarks"></a>Примечания  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **«Внедренный объект»**  
  
-   (необязательно) **«Ссылка на источник»**  
  
 Эти форматы используются для поддержки внедрения и связывания.  
  
##  <a name="a-namecolepastespecialdialoga--colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog  
 Создает объект `COlePasteSpecialDialog`.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Создание флага, содержит любое количество следующих флагов, объединенные с помощью оператора побитового или:  
  
- `PSF_SELECTPASTE`Указывает, что переключатель «вставить», будет проверен изначально при вызове диалогового. Нельзя использовать в сочетании с `PSF_SELECTPASTELINK`. Это значение по умолчанию.  
  
- `PSF_SELECTPASTELINK`Указывает, что связать, переключатель будет проверять изначально при вызове диалоговое окно. Нельзя использовать в сочетании с `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON`Указывает, что флажок виде значка будет проверяться изначально при вызове диалоговое окно.  
  
- `PSF_SHOWHELP`Указывает, что «Справка» будет отображаться при вызове диалоговое окно.  
  
 `pDataObject`  
 Указывает [COleDataObject](../../mfc/reference/coledataobject-class.md) для вставки. Если это значение равно **NULL**, она возвращает `COleDataObject` из буфера обмена.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COlePasteSpecialDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) перечислимый тип в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreateitema--colepastespecialdialogcreateitem"></a><a name="createitem"></a>COlePasteSpecialDialog::CreateItem  
 Создает новый элемент, который был выбран в диалоговом окне Специальная вставка.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pNewItem*  
 Указывает `COleClientItem` экземпляра. Не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только после [DoModal](#domodal) возвращает **IDOK**.  
  
##  <a name="a-namedomodala--colepastespecialdialogdomodal"></a><a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 Отображает диалоговое окно OLE Специальная вставка.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_ps](#m_ps) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
##  <a name="a-namegetdrawaspecta--colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 Определяет, если пользователь выбрал для отображения выбранного элемента в виде значка.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод, необходимых для визуализации объекта.  
  
- `DVASPECT_CONTENT`Возвращается, если флажок виде значка не был установлен при отклонении диалоговое окно.  
  
- `DVASPECT_ICON`Возвращается, если был установлен флажок виде значка, при отклонении диалоговое окно.  
  
### <a name="remarks"></a>Примечания  
 Только эта функция после [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения о рисовании аспект см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegeticonicmetafilea--colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 Возвращает метафайла, связанные с элемента, выбранного пользователем.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий значками аспектом выбранного элемента, если был установлен флажок виде значка при отклонении диалоговое окно, выбрав **ОК**; в противном случае **NULL**.  
  
##  <a name="a-namegetpasteindexa--colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 Возвращает индекс значение, связанное с записью выбранного пользователя.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс в массиве **OLEUIPASTEENTRY** структуры, выбранные пользователем. Следует использовать формат, который соответствует индексу, выбранный при выполнении операции вставки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetselectiontypea--colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType  
 Определяет тип выбора, сделанного пользователем.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип выбора, сделанного.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый тип значений определяется **выбора** перечисления тип, объявленный в `COlePasteSpecialDialog` класса.  
  
 `enum Selection`  
  
 `{`  
  
 `pasteLink,`  
  
 `pasteNormal,`  
  
 `pasteOther,`  
  
 `pasteStatic`  
  
 `};`  
  
 Выполните краткое desccriptions из следующих значений:  
  
- **COlePasteSpecialDialog::pasteLink** установлен переключатель, связать и выбранным форматом был стандартный формат OLE.  
  
- **COlePasteSpecialDialog::pasteNormal** установлен переключатель, вставить и выбранным форматом был стандартный формат OLE.  
  
- **COlePasteSpecialDialog::pasteOther** выбранный формат не является стандартным форматом OLE.  
  
- **COlePasteSpecialDialog::pasteStatic** выбранный формат был метафайл.  
  
##  <a name="a-namempsa--colepastespecialdialogmps"></a><a name="m_ps"></a>COlePasteSpecialDialog::m_ps  
 Структура типа **OLEUIPASTESPECIAL** используется для управления поведением диалогового окна «Специальная вставка».  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить непосредственно или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

