---
title: "Класс COleInsertDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- OLE Insert Object dialog box
- dialog boxes, OLE
- COleInsertDialog class
- Insert Object dialog box
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
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
ms.openlocfilehash: 078f421dacc79ff929249cd35c520b0c4d4a222e
ms.lasthandoff: 02/24/2017

---
# <a name="coleinsertdialog-class"></a>Класс COleInsertDialog
Используется для диалогового окна OLE "Вставить объект".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Создает объект `COleInsertDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|Создание элемента, выбранного в диалоговом окне.|  
|[COleInsertDialog::DoModal](#domodal)|Отображает диалоговое окно Вставка объекта OLE.|  
|[COleInsertDialog::GetClassID](#getclassid)|Возвращает **CLSID** связанный с выбранным элементом.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Сообщает ли для рисования элемента в виде значка.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанные со значками форме этого элемента.|  
|[COleInsertDialog::GetPathName](#getpathname)|Возвращает полный путь к файлу, выбранному в диалоговом окне.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Возвращает тип выбранного объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|Структура типа **OLEUIINSERTOBJECT** , контролирует поведение диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleInsertDialog` когда необходимо вызвать это диалоговое окно предназначено. После `COleInsertDialog` объект был создан, можно использовать [m_io](#m_io) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_io` Структуры имеет тип **OLEUIINSERTOBJECT**. Дополнительные сведения об использовании этого класса диалогового окна в разделе [DoModal](#domodal) функции-члена.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 Эта функция создает только `COleInsertDialog` объекта.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Создание флаг, который содержит любое количество следующих значений для объединения с помощью оператора побитового или:  
  
- **IOF_SHOWHELP** задает отображение кнопки справки при вызове диалоговое окно.  
  
- **IOF_SELECTCREATENEW** указывает, что создать новый переключатель выберет изначально при вызове диалоговое окно. Это значение по умолчанию и не может использоваться с **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** указывает, что переключатель Создать из файла выберет изначально при вызове диалоговое окно. Нельзя использовать с **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** указывает, что флажок связь будет проверяться изначально при вызове диалоговое окно.  
  
- **IOF_DISABLELINK** указывает, что флажок связь будет отключена при вызове диалоговое окно.  
  
- **IOF_CHECKDISPLAYASICON** указывает, что будет изначально установлен флажок виде значка, отображается значок текущего и изменить значок появится кнопка вызова диалогового.  
  
- **IOF_VERIFYSERVERSEXIST** указывает проверки окно классов, он добавляет в список, гарантируя наличие серверов, указанных в базе данных регистрации перед откроется диалоговое окно. Установка этого флажка может существенно снизить общую производительность.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
##  <a name="createitem"></a>COleInsertDialog::CreateItem  
 Эта функция вызывается для создания объекта типа [COleClientItem](../../mfc/reference/coleclientitem-class.md) только тогда, когда [DoModal](#domodal) возвращает **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает для создаваемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо выделить `COleClientItem` объекта перед вызовом этой функции.  
  
##  <a name="domodal"></a>COleInsertDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE вставить объект.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Одно из следующих значений:  
  
 `COleInsertDialog::DocObjectsOnly`вставляет только DocObjects.  
  
 `COleInsertDialog::ControlsOnly`Вставляет элементы управления ActiveX.  
  
 Ноль вставляет DocObject ни элемент управления ActiveX. Это означает в одной и той же реализации как первый прототип перечисленных выше.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
-   IDOK, если успешно откроется диалоговое окно.  
  
-   IDCANCEL, если пользователь отменил диалоговое окно.  
  
-   IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_io](#m_io) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает IDOK, можно вызвать другой член функции для получения параметров или данные, введенные в поле диалогового окна пользователем.  
  
##  <a name="getclassid"></a>COleInsertDialog::GetClassID  
 Эта функция вызывается для получения **CLSID** связанные с выбранного элемента, только если [DoModal](#domodal) возвращает **IDOK** и тип выбора **COleInsertDialog::createNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **CLSID** связанные с выбранным элементом.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 Эта функция вызывается для определения, если пользователь выбрал для отображения выбранного элемента в виде значка.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод, необходимых для визуализации объекта.  
  
- `DVASPECT_CONTENT`Возвращается, если не был установлен флажок виде значка.  
  
- `DVASPECT_ICON`Возвращается, если был установлен флажок виде значка.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции только в том случае, если [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения о рисовании аспект см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуры данных в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 Эта функция вызывается для получения дескриптора метафайла, содержит символическое аспектом выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий значками аспектом выбранного элемента, если флажок виде значка был установлен после закрытия диалогового окна, выбрав **ОК**; в противном случае **NULL**.  
  
##  <a name="getpathname"></a>COleInsertDialog::GetPathName  
 Эта функция вызывается для получения полного пути только если выбранный файл [DoModal](#domodal) возвращает **IDOK** и тип выбора не **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь к файлу, выбранному в диалоговом окне. Если тип выбора `createNewItem`, эта функция возвращает бессмысленной `CString` в режиме выпуска или вызывает проверочное утверждение в режиме отладки.  
  
##  <a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 Эта функция вызывается для получения выбран при отклонении в диалоговом окне Вставка объекта, выбрав тип выбора **ОК**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора, сделанного.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый тип значений определяется **выбора** перечисления тип, объявленный в `COleInsertDialog` класса.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 Выполните краткое описание каждого из этих значений.  
  
- **COleInsertDialog::createNewItem** создать переключатель был выбран.  
  
- **COleInsertDialog::insertFromFile** был выбран переключатель Создать из файла и не был установлен флажок связь.  
  
- **COleInsertDialog::linkToFile** был выбран переключатель Создать из файла и был установлен флажок связь.  
  
##  <a name="m_io"></a>COleInsertDialog::m_io  
 Структура типа **OLEUIINSERTOBJECT** используется для управления поведением в диалоговом окне Вставка объекта.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно изменить члены этой структуры, либо непосредственно, либо с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

