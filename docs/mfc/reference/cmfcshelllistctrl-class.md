---
title: "Класс объект CMFCShellListCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 455ac8911e99843c14cdab80a6c97e243259c5a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcshelllistctrl-class"></a>Объект CMFCShellListCtrl класса
`CMFCShellListCtrl` Класс предоставляет функциональные возможности элемента управления списка Windows и расширяет его, включая возможность отображения списка элементов оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Отображает список элементов, содержащихся в папке, предоставленный.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Отображает список элементов, содержащихся в папке, являющийся родительским для текущей папки.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключает контекстное меню.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Возвращает путь к текущей папке.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Получает имя текущей папки.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Возвращает PIDL текущего списка элемента управления.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Возвращает указатель в текущей папке оболочки.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Возвращает текстовое путь к элементу.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Возвращает типы элементов оболочки, отображаемые элементом управления "список".|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Проверяет, является ли текущую выбранную папку папке на рабочем столе.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Этот метод вызывается платформой при сравнении двух элементов. (Переопределяет [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Вызывается, когда платформа извлекает файл дату, отображаемого элементом управления "список".|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Вызывается, когда платформа преобразует размер файла элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Вызывается, когда платформа получает значок элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Вызывается, когда платформа преобразует текст элемента управления списка.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Вызывается платформой, когда он задает имена столбцов.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Обновляет и обновляет элемент управления списка.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Задает тип элементов, отображаемого элементом управления "список".|  
  
## <a name="remarks"></a>Примечания  
 `CMFCShellListCtrl` Класс расширяет функциональность [CMFCListCtrl класса](../../mfc/reference/cmfclistctrl-class.md) путем включения программы для получения списка элементов оболочки Windows. Формат отображения, который используется аналогичен синтаксису представления списка для проводника.  
  
 Объект [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) может быть связан с `CMFCShellListCtrl` объект для создания полного окна обозревателя. Затем, при выборе элемента в `CMFCShellTreeCtrl` вызовет `CMFCShellListCtrl` объекта, чтобы вывести содержимое выбранного элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать объект `CMFCShellListCtrl` и способ отображения родительскую папку для текущей папки. Этот фрагмент кода является частью [пример анализатора](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]  
  
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
 Отображает список элементов, содержащихся в папке предоставленного.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPath`  
 Строка, содержащая путь к папке.  
  
 [in] `lpItemInfo`  
 Указатель на `LPAFX_SHELLITEMINFO` структура, описывающая папки для просмотра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; `E_FAIL` в противном случае.  
  
##  <a name="displayparentfolder"></a>CMFCShellListCtrl::DisplayParentFolder  
 Обновления [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта, чтобы открыть родительскую папку для текущей папки.  
  
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
 Возвращает путь к выбранной папке в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strPath`  
 Ссылка на строковый параметр, где метод записывает путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если папка не выбрана в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentfoldername"></a>CMFCShellListCtrl::GetCurrentFolderName  
 Получает имя текущей выбранной папки в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strName`  
 Ссылка на строковый параметр, где метод записывает имя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если папка не выбрана в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentitemidlist"></a>CMFCShellListCtrl::GetCurrentItemIdList  
 Возвращает PIDL текущего выбранного элемента.  
  
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
 Получает пути к элементу.  
  
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
 Индекс, предоставляемые `iItem` основан на элементах, отображаемую в данный момент с [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
##  <a name="getitemtypes"></a>CMFCShellListCtrl::GetItemTypes  
 Возвращает тип элементов, отображаемых на [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539) значение, содержащее тип элементов, перечисленных в `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать тип элементов в списке `CMFCShellListCtrl`, вызовите [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="isdesktop"></a>CMFCShellListCtrl::IsDesktop  
 Определяет папку, отображаемых в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект находится в папке на рабочем столе.  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если отображается папка находится в папке на рабочем столе; `FALSE` в противном случае.  
  
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
 Этот метод вызывается платформой при его необходимо преобразовать дату, связанный с объектом, в строку.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `tmFile`  
 Дата, связанная с файлом.  
  
 [выходной] `str`  
 Строка, содержащая дату форматированный файл.  
  
### <a name="remarks"></a>Примечания  
 Когда [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объекта отображается дата, связанная с файлом, его необходимо преобразовать эту дату в формате строки. `CMFCShellListCtrl` Такое преобразование с помощью этого метода. По умолчанию этот метод использует текущий языковой стандарт для форматирования даты в строку.  
  
##  <a name="onformatfilesize"></a>CMFCShellListCtrl::OnFormatFileSize  
 Этот метод вызывается платформой при преобразует размер объекта в строку.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lFileSize`  
 Размер файла, который будет отображать платформу.  
  
 [выходной] `str`  
 Строка, содержащая форматированный файл размер.  
  
### <a name="remarks"></a>Примечания  
 Когда [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объект должен отображать размер файла, ему необходимо преобразовать размер файла в формате строки. `CMFCShellListCtrl` Такое преобразование с помощью этого метода. По умолчанию этот метод преобразует байт размер файла в килобайтах, а затем использует текущий языковой стандарт для форматирования размер в строку.  
  
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
 Объект `LPAFX_SHELLITEMINFO` параметр, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения значка в случае успешного выполнения; значение -1, если функция завершается с ошибкой.  
  
### <a name="remarks"></a>Примечания  
 Индекс изображения значка основан на списке образ системы.  
  
 По умолчанию этот метод использует `pItem` параметра. Значение `iItem` не используется в реализации по умолчанию. Можно использовать `iItem` для реализации пользовательского поведения.  
  
##  <a name="ongetitemtext"></a>CMFCShellListCtrl::OnGetItemText  
 Этот метод вызывается платформой при его необходимо извлечь текст элемента оболочки.  
  
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
 Требуемого столбца.  
  
 [in] `pItem`  
 Объект `LPAFX_SHELLITEMINFO` параметр, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий текст, связанный с элементом.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в `CMFCShellListCtrl` объекта могут иметься текста в одном или нескольких столбцах. Когда платформа вызывает этот метод, он указывает столбец, который нужно получить. Если вызвать эту функцию вручную, также необходимо указать столбец, который вас интересует.  
  
 По умолчанию этот метод использует `pItem` параметра, чтобы определить, какому элементу процессу. Значение `iItem` не используется в реализации по умолчанию.  
  
##  <a name="onsetcolumns"></a>CMFCShellListCtrl::OnSetColumns  
 Платформа вызывает этот метод, когда он задает имена столбцов.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа создает четыре столбца в `CMFCShellListCtrl` объекта. Эти столбцы называются `Name`, `Size`, `Type`, и `Modified`. Можно переопределить этот метод, чтобы настроить количество столбцов и их имена.  
  
##  <a name="refresh"></a>CMFCShellListCtrl::Refresh  
 Обновляет и обновляет [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; в противном случае — значение ошибки.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы обновить список элементов, отображаемых на `CMFCShellListCtrl` объекта.  
  
##  <a name="setitemtypes"></a>CMFCShellListCtrl::SetItemTypes  
 Задает тип элементов, которые перечислены в [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTypes`  
 Список элементов типов, `CMFCShellListCtrl` поддерживает.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о списке типов элементов, см. в разделе [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)   
 [Класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)
