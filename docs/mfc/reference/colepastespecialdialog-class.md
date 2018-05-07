---
title: Класс COlePasteSpecialDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2e668a2ad15ec9ec2fb779be32d35c17eb57cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="colepastespecialdialog-class"></a>Класс COlePasteSpecialDialog
Используется для диалогового окна OLE "Вставить специальный объект".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Создает объект `COlePasteSpecialDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Добавляет в список форматов, которые можно вставить в приложение пользовательские форматы.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Добавляет новую запись в список поддерживаемых форматов буфера обмена.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Добавляет **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`и при необходимости `CF_LINKSOURCE` список форматов можно вставить приложения.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Создает элемент в документе-контейнере, используя указанный формат.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Отображает диалоговое окно OLE Специальная вставка.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Сообщает ли рисование элементов в виде значка или нет.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Возвращает индекс параметры вставки доступен, выбранного пользователем.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Возвращает тип выбранного фрагмента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Структура типа **OLEUIPASTESPECIAL** , который управляет функция диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COlePasteSpecialDialog` при необходимости вызовите данным диалоговым окном. После `COlePasteSpecialDialog` объект был создан, можно использовать [AddFormat](#addformat) и [AddStandardFormats](#addstandardformats) функции-члены для добавления форматы буфера обмена в диалоговое окно. Можно также использовать [m_ps](#m_ps) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ps` Структуры имеет тип **OLEUIPASTESPECIAL**.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) структуры в Windows SDK.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
  
##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat  
 Вызывайте эту функцию, чтобы добавить новые форматы список форматов, которые приложение может поддерживать в Специальная вставка операции.  
  
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
 Различные параметры связывания и внедрения для данного формата. Этот флаг представляет собой битовую комбинацию из одного или нескольких различных значений в **OLEUIPASTEFLAG** перечисляемый тип.  
  
 `cf`  
 Используемый формат буфера обмена.  
  
 *tymed*  
 Типы мультимедиа, доступные в этом формате. Это представляет собой битовую комбинацию из одного или нескольких значений в **TYMED** перечисляемый тип.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат. Формат данной строки — это две отдельные строки, разделенные символом «\n». Первая строка имеет те же данные, должны быть переданы в *lpstrFormat* параметра, а вторая совпадает со значением *lpstrResult* параметра.  
  
 *bEnableIcon*  
 Флаг, который определяет, включен ли флажок виде значка при выборе этот формат в поле со списком.  
  
 *bLink*  
 Флаг, который определяет, включен ли переключатель связать при выборе этот формат в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Эта функция может вызываться для добавления либо стандартные форматы, такие как **CF_TEXT** или **CF_TIFF** или пользовательских форматов, зарегистрированных в приложение с системой. Дополнительные сведения о вставке данных объектов в приложении см. в статье [объекты и источники данных: обработка](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Дополнительные сведения см. в разделе [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) тип перечисления и [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) перечисляемый тип в Windows SDK.  
  
##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry  
 Добавляет новую запись в список поддерживаемых форматов буфера обмена.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 Используемый формат буфера обмена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) структуру, содержащую сведения для новой записи ссылки.  
  
##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats  
 Вызывайте эту функцию, чтобы добавить следующие форматы буфера обмена в список форматов, которые приложение может поддерживать в Специальная вставка операции:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableLink*  
 Флаг, определяющий, следует ли добавить `CF_LINKSOURCE` список форматов можно вставить приложения.  
  
### <a name="remarks"></a>Примечания  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **«Внедренный объект»**  
  
-   (необязательно) **«Связать источник»**  
  
 Эти форматы используются для поддержки внедренных и связанных объектов.  
  
##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog  
 Создает объект `COlePasteSpecialDialog`.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Флаг создания содержит произвольное количество комбинируются с помощью оператора побитового или следующие флаги:  
  
- `PSF_SELECTPASTE` Указывает, что переключатель «вставить» будет проверяться изначально при вызове диалогового. Нельзя использовать в сочетании с `PSF_SELECTPASTELINK`. Это значение по умолчанию.  
  
- `PSF_SELECTPASTELINK` Указывает, что Вставить связь, переключатель будет проверять изначально при вызове диалоговым окном. Нельзя использовать в сочетании с `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON` Указывает, что флажок виде значка будет проверяться изначально при вызове диалоговым окном.  
  
- `PSF_SHOWHELP` Задает отображение кнопки справки при вызове диалоговым окном.  
  
 `pDataObject`  
 Указывает на [COleDataObject](../../mfc/reference/coledataobject-class.md) для вставки. Если это значение равно **NULL**, он получает `COleDataObject` из буфера обмена.  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Только эта функция создает `COlePasteSpecialDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) перечисляемый тип в Windows SDK.  
  
##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem  
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
 Эту функцию следует вызывать только после [DoModal](#domodal) возвращает **IDOK**.  
  
##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal  
 Отображает диалоговое окно OLE Специальная вставка.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_ps](#m_ps) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect  
 Определяет, если пользователь выбрал Отображение выбранного элемента в виде значка.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод требуется для отображения объекта.  
  
- `DVASPECT_CONTENT` Возвращается, если флажок виде значка не был установлен при отклонении диалоговым окном.  
  
- `DVASPECT_ICON` Возвращается, если был установлен флажок виде значка, когда диалоговое окно было отклонено.  
  
### <a name="remarks"></a>Примечания  
 Только эта функция после [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения о рисовании аспект см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры в Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile  
 Возвращает метафайла, связанные с элемента, выбранного пользователем.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий преобразованного в значок аспектом выбранного элемента, если был установлен флажок виде значка, когда диалоговое окно было отклонено, выбрав **ОК**; в противном случае **NULL**.  
  
##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex  
 Возвращает индекс значение, связанное с записью выбрал пользователь.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс в массиве **OLEUIPASTEENTRY** структуры, выбранные пользователем. Следует использовать формат, который соответствует индексу, выбранного при выполнении операции вставки.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) структуры в Windows SDK.  
  
##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType  
 Определяет тип выбора, сделанного пользователем.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип выбора объектов.  
  
### <a name="remarks"></a>Примечания  
 Тип возвращаемого значения задаются **выбора** тип перечисления, объявленный в `COlePasteSpecialDialog` класса.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 Выполните краткое desccriptions из следующих значений:  
  
- **COlePasteSpecialDialog::pasteLink** установлен переключатель, связать и выбранным форматом был стандартный формат OLE.  
  
- **COlePasteSpecialDialog::pasteNormal** установлен переключатель, вставки и выбранным форматом был стандартный формат OLE.  
  
- **COlePasteSpecialDialog::pasteOther** выбранный формат не стандартный формат OLE.  
  
- **COlePasteSpecialDialog::pasteStatic** выбранным форматом был метафайл.  
  
##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps  
 Структура типа **OLEUIPASTESPECIAL** используется для управления поведением Специальная вставка диалогового окна.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить непосредственно или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) структуры в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
