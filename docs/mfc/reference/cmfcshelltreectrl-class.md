---
title: "Класс CMFCShellTreeCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellTreeCtrl class
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cf9c7c3577646895546c443c975a92431194d3f4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcshelltreectrl-class"></a>Класс CMFCShellTreeCtrl
`CMFCShellTreeCtrl` Расширяет класс [класс CTreeCtrl](../../mfc/reference/ctreectrl-class.md) функциональность, отображая иерархию элементов оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключает контекстное меню.|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Возвращает сочетание флагов, которые передаются [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Возвращает путь к элементу.|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Возвращает указатель на [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объект, используемый вместе с это `CMFCShellTreeCtrl` объекта для создания окна проводника.|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Эта функция-член вызывается родительского окна, когда получает сообщение уведомления, которое применяется к этому окну. (Переопределяет [CWnd::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|Обновление и обновляет текущий `CMFCShellTreeCtrl` объекта.|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Выбор соответствующего дерева элемента управления, на основе предоставленного PIDL или строкой пути.|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Задает флаги для дерева контекст фильтра (аналогично флаги, используемые `IShellFolder::EnumObjects`).|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Задает связь между текущим `CMFCShellTreeCtrl` объекта и `CMFCShellListCtrl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс расширяет `CTreeCtrl` класса, позволяя программе для включения в дереве элементов оболочки Windows. Этот класс может быть связан с `CMFCShellListCtrl` объекта для создания полного окна обозревателя. Затем при выборе элемента в дереве будет отображен список элементов оболочки Windows в связанном списке.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxshelltreeCtrl.h  
  
## <a name="example"></a>Пример  
 В следующем примере показывается, как создать объект класса `CMFCShellTreeCtrl`. Этот фрагмент кода является частью [Образец проводника](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer&#4;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer&#5;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl::EnableShellContextMenu  
 Позволяет в контекстном меню.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логическое значение, указывающее, следует ли включить в контекстном меню.  
  
##  <a name="getflags"></a>CMFCShellTreeCtrl::GetFlags  
 Возвращает флаги, установленные для [CMFCShellTreeCtrl класс](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` задано значение, указывающее сочетание флагов, в настоящее время.  
  
### <a name="remarks"></a>Примечания  
 Флаги `CMFCShellTreeCtrl` передаются в метод [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) при каждом обновлении объекта. Вы можете изменить флаги, с помощью [CMFCShellTreeCtrl::SetFlags](#setflags) метод.  
  
##  <a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath  
 Получает путь к элементу в [CMFCShellTreeCtrl класс](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strPath`  
 Ссылка на строковый параметр. Метод записывает путь элемента для данного параметра.  
  
 [in] `htreeItem`  
 Метод возвращает путь для элемента управления дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод не удается, `strPath` содержит пустую строку.  
  
 Если вы не укажете `hTreeItem`, этот метод пытается получить строку для выбранного элемента. Если элемент не выбран и `hTreeItem` — `NULL`, этот метод не дает результата.  
  
##  <a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList  
 Возвращает указатель на [объект CMFCShellListCtrl класс](../../mfc/reference/cmfcshelllistctrl-class.md) объект, связанный с этим [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMFCShellListCtrl` объект, связанный с данным объектом управления дерева.  
  
### <a name="remarks"></a>Примечания  
 С помощью `CMFCShellListCtrl` объекта вместе с `CMFCShellTreeCtrl` объекта, можно создать окно проводника. Используйте метод [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) для связывания двух классов. После они связаны, платформа автоматически обновляет `CMFCShellListCtrl` если выделение в `CMFCShellTreeCtrl` изменения.  
  
##  <a name="onchildnotify"></a>CMFCShellTreeCtrl::OnChildNotify  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pLResult);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `message`  
 [in] `wParam`  
 [in] `lParam`  
 [in] `pLResult`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ongetitemicon"></a>CMFCShellTreeCtrl::OnGetItemIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pItem`  
 [in] `bSelected`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ongetitemtext"></a>CMFCShellTreeCtrl::OnGetItemText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pItem`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="refresh"></a>CMFCShellTreeCtrl::Refresh  
 Обновление и обновляет [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода позволяет обновить иерархию элементов, отображаемых в `CMFCShellTreeCtrl`.  
  
##  <a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath  
 Выбирает элемент в [CMFCShellTreeCtrl класс](../../mfc/reference/cmfcshelltreectrl-class.md) на основе указанного пути.  
  
```  
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPath`  
 Строка, указывающая путь к элементу.  
  
 [in] `lpidl`  
 PIDL, который указывает элемент  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения; `E_FAIL` в противном случае.  
  
##  <a name="setflags"></a>CMFCShellTreeCtrl::SetFlags  
 Задает флаги для дерева контекст фильтра.  
  
```  
void SetFlags(
    DWORD dwFlags,  
    BOOL bRefresh = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwFlags`  
 Флажки, которые нужно установить.  
  
 [in] `bRefresh`  
 Логическое значение, указывающее, является ли `CMFCShellTreeCtrl` должен быть обновлен немедленно.  
  
### <a name="remarks"></a>Примечания  
 `CMFCShellTreeCtrl` Передает все установить флаги для [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Дополнительные сведения о значениях различных флагов см. в разделе [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList  
 Связывает [объект CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) объекта с [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) объекта.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pShellList`  
 Указатель на объект `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод связывает `CMFCShellListCtrl` с `CMFCShellTreeCtrl`. Эти объекты могут быть отображены как окно проводника: Если пользователь выбирает объект в `CMFCShellTreeCtrl`, связанные элементы в `CMFCShellListCtrl` будет автоматически обновлена.  
  
 Используйте метод [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) для получения `CMFCShellListCtrl` связанных с `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl-класс](../../mfc/reference/ctreectrl-class.md)   
 [Объект CMFCShellListCtrl класса](../../mfc/reference/cmfcshelllistctrl-class.md)

