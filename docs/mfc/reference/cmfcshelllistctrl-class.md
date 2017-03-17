---
title: "Класс объект CMFCShellListCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellListCtrl class
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
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
ms.openlocfilehash: 8adac043d30d7555522c05165ffd3856c5999872
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcshelllistctrl-class"></a>Объект CMFCShellListCtrl класса
`CMFCShellListCtrl` Класс предоставляет функциональные возможности элемента управления списка Windows и расширяет, включая возможность отображения списка элементов оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Отображает список элементов, содержащихся в указанных папок.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Отображает список элементов, содержащихся в папке, являющейся родительской папки, выделенного в настоящий момент.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключает контекстное меню.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Получает путь к текущей папке.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Получает имя текущей папки.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Возвращает PIDL текущего элемента управления списка.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Возвращает указатель в текущей папке оболочки.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Возвращает текстовое путь к элементу.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Возвращает типы элементов оболочки, отображаемые в элементе управления списком.|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Проверяет, является ли текущую выбранную папку папке на рабочем столе.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Платформа вызывает этот метод, когда он сравнивает два элемента. (Переопределяет [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Вызывается, когда платформа извлекает файл Дата отображается с помощью элемента управления списка.|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Вызывается, когда платформа преобразует размер файла элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Вызывается, когда платформа получает значок элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Вызывается, когда платформа преобразовывает текст элемента управления списка.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Вызывается платформой, когда он задает имена столбцов.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Обновление и обновляет элемент управления списка.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Задает тип элементов, отображаемых в элементе управления списком.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCShellListCtrl` Класс расширяет функциональные возможности [CMFCListCtrl класса](../../mfc/reference/cmfclistctrl-class.md) , позволяя программе для получения списка элементов оболочки Windows. Формат отображения, который используется аналогично, представление списка для окно проводника.  
  
 Объект [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) может быть связан с `CMFCShellListCtrl` объекта для создания полного окна обозревателя. Выбрав элемент в `CMFCShellTreeCtrl` вызовет `CMFCShellListCtrl` объекта, чтобы вывести содержимое выбранного элемента.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCShellListCtrl` класса и отображение родительской папки текущей папки. Этот фрагмент кода является частью [Образец проводника](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer&#1;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer&#2;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer&#3;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 `CMFCShellListCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxshelllistCtrl.h  
  
##  <a name="displayfolder"></a>CMFCShellListCtrl::DisplayFolder  
 Отображает список элементов, содержащихся в папке предоставленный.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPath`  
 Строка, содержащая путь к папке.  
  
 [in] `lpItemInfo`  
 Указатель на `LPAFX_SHELLITEMINFO` структура, описывающая папку для отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; `E_FAIL` в противном случае.  
  
##  <a name="displayparentfolder"></a>CMFCShellListCtrl::DisplayParentFolder  
 Обновления [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект для отображения родительской папки текущей папки.  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; `E_FAIL` в противном случае.  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellListCtrl::EnableShellContextMenu  
 Позволяет в контекстном меню.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логическое значение, указывающее, включает ли платформа в контекстном меню.  
  
##  <a name="getcurrentfolder"></a>CMFCShellListCtrl::GetCurrentFolder  
 Получает путь к папке, выбранной в настоящее время в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strPath`  
 Ссылка на строковый параметр, где метод записывает путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если нет папки, выбранной в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentfoldername"></a>CMFCShellListCtrl::GetCurrentFolderName  
 Получает имя текущей выбранной папки в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strName`  
 Ссылка на строковый параметр, где метод записывает имя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если нет папки, выбранной в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentitemidlist"></a>CMFCShellListCtrl::GetCurrentItemIdList  
 Возвращает PIDL элемента, выбранного в данный момент.  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 PIDL текущего элемента.  
  
##  <a name="getcurrentshellfolder"></a>CMFCShellListCtrl::GetCurrentShellFolder  
 Возвращает указатель на текущий выбранный элемент в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IShellFolder интерфейс](http://msdn.microsoft.com/library/windows/desktop/bb775075) для выбранного объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `NULL` , если объект не выбран в данный момент.  
  
##  <a name="getitempath"></a>CMFCShellListCtrl::GetItemPath  
 Получает путь для элемента.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    int iItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strPath`  
 Ссылка на строку, которая получает путь.  
  
 [in] `iItem`  
 Индекс элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Индекс, предоставляемые `iItem` основана на элементы, отображаемые в данный момент [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
##  <a name="getitemtypes"></a>CMFCShellListCtrl::GetItemTypes  
 Возвращает тип элементов, отображаемых по [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539) значение, содержащее тип элементов, перечисленных в `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать тип элементов, перечисленных в `CMFCShellListCtrl`, вызовите [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="isdesktop"></a>CMFCShellListCtrl::IsDesktop  
 Определяет папку, отображаются в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект находится в папке на рабочем столе.  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если отображается папка — системная папка; `FALSE` в противном случае.  
  
##  <a name="oncompareitems"></a>CMFCShellListCtrl::OnCompareItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lParam1`  
 [in] `lParam2`  
 [in] `iColumn`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onformatfiledate"></a>CMFCShellListCtrl::OnFormatFileDate  
 Платформа вызывает этот метод, когда его необходимо преобразовать дату, связанный с объектом, в строку.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `tmFile`  
 Дата, связанная с файлом.  
  
 [выходной] `str`  
 Строка, содержащая файл в формате даты.  
  
### <a name="remarks"></a>Примечания  
 Когда [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объекта отображается дата, связанная с файлом, его необходимо преобразовать эту дату в строковом формате. `CMFCShellListCtrl` Преобразования с помощью этого метода. По умолчанию этот метод использует текущий языковой стандарт для форматирования даты в строку.  
  
##  <a name="onformatfilesize"></a>CMFCShellListCtrl::OnFormatFileSize  
 Платформа вызывает этот метод, когда преобразует размер объекта в строку.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lFileSize`  
 Размер файла, которое будет отображаться в платформе.  
  
 [выходной] `str`  
 Строка, содержащая размер файла формате.  
  
### <a name="remarks"></a>Примечания  
 Когда [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объекта требуется для отображения размера файла, для преобразования размер файла в формате строки. `CMFCShellListCtrl` Преобразования с помощью этого метода. По умолчанию этот метод преобразует размера файла из байтов в килобайтах, а затем использует текущий языковой стандарт для форматирования размер в строку.  
  
##  <a name="ongetitemicon"></a>CMFCShellListCtrl::OnGetItemIcon  
 Платформа вызывает этот метод, чтобы получить значок, связанный с элементом списка оболочки.  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iItem`  
 Индекс элемента.  
  
 [in] `pItem`  
 A `LPAFX_SHELLITEMINFO` параметр, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения значка в случае успешного выполнения; значение -1, если функция завершается с ошибкой.  
  
### <a name="remarks"></a>Примечания  
 Индекс изображения значка основан на списке образ системы.  
  
 По умолчанию этот метод использует `pItem` параметр. Значение `iItem` не используется в реализации по умолчанию. Можно использовать `iItem` для реализации пользовательского поведения.  
  
##  <a name="ongetitemtext"></a>CMFCShellListCtrl::OnGetItemText  
 Платформа вызывает этот метод, когда приложению необходимо получить текст элемента оболочки.  
  
```  
virtual CString OnGetItemText(
    int iItem,  
    int iColumn,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iItem`  
 Индекс элемента.  
  
 [in] `iColumn`  
 Столбец процентов.  
  
 [in] `pItem`  
 A `LPAFX_SHELLITEMINFO` параметр, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий текст, связанный с элементом.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в `CMFCShellListCtrl` объекта могут иметься текста в одном или нескольких столбцах. Когда платформа вызывает этот метод, он указывает столбец, который интересующие его. Если вызвать эту функцию вручную, также необходимо указать столбец, который вас интересует.  
  
 По умолчанию этот метод использует `pItem` параметр, чтобы определить, какому элементу процессу. Значение `iItem` не используется в реализации по умолчанию.  
  
##  <a name="onsetcolumns"></a>CMFCShellListCtrl::OnSetColumns  
 Платформа вызывает этот метод, когда он задает имена столбцов.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа создает четыре столбца в `CMFCShellListCtrl` объекта. Эти столбцы называются `Name`, `Size`, `Type`, и `Modified`. Можно переопределить этот метод, чтобы настроить количество столбцов и их имена.  
  
##  <a name="refresh"></a>CMFCShellListCtrl::Refresh  
 Обновление и обновляет [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; в противном случае — значение ошибки.  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода позволяет обновить список элементов, отображаемых по `CMFCShellListCtrl` объекта.  
  
##  <a name="setitemtypes"></a>CMFCShellListCtrl::SetItemTypes  
 Задает тип элементов, которые перечислены в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTypes`  
 Список элементов на типы, которые `CMFCShellListCtrl` поддерживает.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о списке типов элементов, см. в разделе [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)   
 [Класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)

