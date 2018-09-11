---
title: Класс CMFCShellListCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aef6192218f5fae40bca6aa6fb8202a0d238091a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195836"
---
# <a name="cmfcshelllistctrl-class"></a>Класс CMFCShellListCtrl
`CMFCShellListCtrl` Класс предоставляет функциональные возможности элемента управления списка Windows и расширяет его, включив возможность отображения списка элементов оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Отображает список элементов, содержащихся в предоставленный папке.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Отображает список элементов, содержащихся в папке, который является родительским для текущей отображаемой папки.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключает контекстное меню.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Извлекает путь к текущей папке.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Получает имя текущей папки.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Возвращает PIDL текущего элемента управления списка.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Возвращает указатель в текущую папку оболочки.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Возвращает текстовое путь элемента.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Возвращает типы элементов оболочки для отображения в элементе управления списком.|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Проверяет, является ли текущую выбранную папку в папке рабочего стола.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Этот метод вызывается платформой при сравнении двух элементов. (Переопределяет [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Вызывается, когда платформа извлекает дата файла, отображаемого элементом управления списка.|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Вызывается, когда инфраструктура службы преобразует размер файла элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Вызывается, когда платформа возвращает значок элемента управления списка.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Вызывается, когда инфраструктура службы преобразует текст элемента управления списка.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Вызывается платформой, когда он задает имена столбцов.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Обновляет и обновляет элемент управления списка.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Задает тип элементов, отображаемых элементом управления списка.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCShellListCtrl` Класс расширяет функциональность [класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md) , включив программы для получения списка элементов оболочки Windows. Формат отображения, который используется аналогичен синтаксису представления списка для окно проводника.  
  
 Объект [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) может быть связан с `CMFCShellListCtrl` объекта, чтобы создать полный окно обозревателя. Затем, при выборе элемента в `CMFCShellTreeCtrl` вызовет `CMFCShellListCtrl` для перечисления содержимого выбранного элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать объект `CMFCShellListCtrl` класс и способ отображения родительской папки, отображаемой папки. Этот фрагмент кода является частью [пример Explorer](../../visual-cpp-samples.md).  
  
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
  
##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder  
 Отображает список элементов, содержащихся в папке предоставленного.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszPath*  
 Строка, содержащая путь к папке.  
  
 [in] *lpItemInfo*  
 Указатель на `LPAFX_SHELLITEMINFO` структура, описывающая папку для отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; В противном случае — значение E_FAIL.  
  
##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder  
 Обновления [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект для отображения родительской папки, отображаемой папки.  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; В противном случае — значение E_FAIL.  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu  
 Позволяет в контекстном меню.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Логическое значение, указывающее, включает ли платформа в контекстном меню.  
  
##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder  
 Извлекает путь к выбранной папке в [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *strPath*  
 Ссылка на строковый параметр, где метод записывает путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнение прошло успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если папка не выбрана в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName  
 Извлекает имя текущую выбранную папку в [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *strName*  
 Ссылка на строковый параметр, где метод записывает имя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнение прошло успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если папка не выбрана в `CMFCShellListCtrl`.  
  
##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList  
 Возвращает PIDL текущего выбранного элемента.  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 PIDL текущего элемента.  
  
##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder  
 Возвращает указатель на текущий выбранный элемент в [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IShellFolder интерфейс](https://msdn.microsoft.com/library/windows/desktop/bb775075) для выбранного объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение NULL, если объект не выбран в данный момент.  
  
##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath  
 Возвращает путь для элемента.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    int iItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *strPath*  
 Ссылка на строку, которая получает путь.  
  
 [in] *iItem*  
 Индекс элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если выполнение прошло успешно; Значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Индекс, переданный по *iItem* основан на элементах, отображаемый в настоящий момент [класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes  
 Возвращает тип элементов, отображаемых на [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf) значение, содержащее тип элементов, перечисленных в `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать тип элементов, перечисленных в `CMFCShellListCtrl`, вызовите [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop  
 Определяет папку, является ли отображаться в [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект находится в папке рабочего стола.  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если отображаемой папки папке рабочего стола; Значение FALSE в противном случае.  
  
##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lParam1*  
 [in] *lParam2*  
 [in] *iColumn*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate  
 Этот метод вызывается платформой при его необходимо преобразовать эту дату, связанный с объектом, в строку.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *tmFile*  
 Дата, связанная с файлом.  
  
 [out] *str*  
 Строка, содержащая файла в формате даты.  
  
### <a name="remarks"></a>Примечания  
 Когда [класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта отображается дата, связанных с файлом, его необходимо преобразовать эту дату в строковом формате. `CMFCShellListCtrl` Использует этот метод, чтобы сделать это преобразование. По умолчанию этот метод использует текущий языковой стандарт для форматирования даты в строку.  
  
##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize  
 Этот метод вызывается платформой при преобразовании размер объекта в строку.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lFileSize*  
 Размер файла, который будет отображаться платформы.  
  
 [out] *str*  
 Строка, содержащая размер файла в формате.  
  
### <a name="remarks"></a>Примечания  
 Когда [класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объект должен отображать размера файла, его необходимо преобразовать размер файла в строковом формате. `CMFCShellListCtrl` Использует этот метод, чтобы сделать это преобразование. По умолчанию этот метод преобразует размер файла из байтов в килобайтах, а затем использует текущий языковой стандарт для форматирования размер в строку.  
  
##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon  
 Платформа вызывает этот метод, чтобы получить значок, связанный с элементом списка оболочки.  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iItem*  
 Индекс элемента.  
  
 [in] *pItem*  
 Параметр LPAFX_SHELLITEMINFO, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения значка, если выполнение прошло успешно; -1, если функция завершается с ошибкой.  
  
### <a name="remarks"></a>Примечания  
 Индекс изображения значка основана на списке образ системы.  
  
 По умолчанию этот метод использует *pItem* параметра. Значение *iItem* не используется в реализации по умолчанию. Можно использовать *iItem* для реализации пользовательского поведения.  
  
##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText  
 Этот метод вызывается платформой, когда он должен извлекать текст элемента оболочки.  
  
```  
virtual CString OnGetItemText(
    int iItem,  
    int iColumn,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iItem*  
 Индекс элемента.  
  
 [in] *iColumn*  
 Требуемого столбца.  
  
 [in] *pItem*  
 Параметр LPAFX_SHELLITEMINFO, который описывает элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий текст, связанный с элементом.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в `CMFCShellListCtrl` объекта могут иметься текста в одном или нескольких столбцах. Когда платформа вызывает этот метод, он указывает столбец, который интересующие его. Если вы вызываете эту функцию вручную, необходимо также указать столбец, которые вас интересуют.  
  
 По умолчанию этот метод использует *pItem* параметр, чтобы определить, какому элементу к процессу. Значение *iItem* не используется в реализации по умолчанию.  
  
##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns  
 Этот метод вызывается платформой при задании имен столбцов.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа создает четыре столбца в `CMFCShellListCtrl` объекта. Имена этих столбцов являются **имя**, **размер**, **тип**, и **Modified**. Можно переопределить этот метод, чтобы настроить количество столбцов и их имена.  
  
##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh  
 Обновляет и обновляет [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если выполнение прошло успешно; в противном случае значение ошибки.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы обновить список элементов, отображаемых на `CMFCShellListCtrl` объекта.  
  
##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes  
 Задает тип элементов, перечисленных в [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nTypes*  
 Список элементов на типы, которые `CMFCShellListCtrl` поддерживает.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о списке типов элементов, см. в разделе [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)   
 [Класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)
