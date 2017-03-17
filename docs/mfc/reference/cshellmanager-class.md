---
title: "Класс CShellManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
dev_langs:
- C++
helpviewer_keywords:
- CShellManager class
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bf6be5c0d106344024d32e90cc6cfb1e3299075
ms.lasthandoff: 02/24/2017

---
# <a name="cshellmanager-class"></a>Класс CShellManager
Реализует несколько методов, которые позволяют работать с указателями в списках идентификаторов (PIDL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Создает объект `CShellManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Отображает диалоговое окно, которое позволяет пользователю выбрать папку оболочки.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Сцепляет два Pidl.|  
|[CShellManager::CopyItem](#copyitem)|Создает новый PIDL и копирует предоставленный PIDL на него.|  
|[CShellManager::CreateItem](#createitem)|Создает новый PIDL указанного размера.|  
|[CShellManager::FreeItem](#freeitem)|Удаляет указанный PIDL.|  
|[CShellManager::GetItemCount](#getitemcount)|Возвращает количество элементов в указанный PIDL.|  
|[CShellManager::GetItemSize](#getitemsize)|Возвращает размер предоставленного PIDL.|  
|[CShellManager::GetNextItem](#getnextitem)|Возвращает следующий элемент из PIDL.|  
|[CShellManager::GetParentItem](#getparentitem)|Получает родительский элемент указанного элемента.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Извлекает PIDL для элемента, определяемого по указанному пути.|  
  
## <a name="remarks"></a>Примечания  
 Методы `CShellManager` класса все приходится иметь дело с Pidl. PIDL — это уникальный идентификатор для объекта оболочки.  
  
 Не следует создавать `CShellManager` объекта вручную. Он будет создан автоматически платформой приложения. Тем не менее, следует вызывать [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) во время инициализации приложения. Чтобы получить указатель диспетчера оболочки для вашего приложения, вызовите [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 Отображает диалоговое окно, которое позволяет пользователю выбрать папку оболочки.  
  
```  
BOOL BrowseForFolder(
    CString& strOutFolder,  
    CWnd* pWndParent = NULL,  
    LPCTSTR lplszInitialFolder = NULL,  
    LPCTSTR lpszTitle = NULL,  
    UINT ulFlags = BIF_RETURNONLYFSDIRS,  
    LPINT piFolderImage = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strOutFolder`  
 Строка, используемая при помощи метода для сохранения пути к выбранной папке.  
  
 [in] `pWndParent`  
 Указатель на родительское окно.  
  
 [in] `lplszInitialFolder`  
 Строка, содержащая папку, установлен по умолчанию, когда отображается диалоговое окно.  
  
 [in] `lpszTitle`  
 Заголовок диалогового окна.  
  
 [in] `ulFlags`  
 Флаги, определяющие параметры для диалогового окна. В разделе [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) подробное описание.  
  
 [выходной] `piFolderImage`  
 Указатель на целое значение, где метод записывает индекс изображения выбранной папки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает папки из диалогового окна; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При вызове этого метода приложение создается и отображается диалоговое окно, которое позволяет пользователю выбрать папку. Метод запишет путь к папке в `strOutFolder` параметр.  
  
### <a name="example"></a>Пример  
 Ниже приведен пример, как получить ссылку на `CShellManager` объекта с помощью `CWinAppEx::GetShellManager` метода и как использовать `BrowseForFolder` метод. Этот фрагмент кода является частью [Образец проводника](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer №&6;](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>CShellManager::ConcatenateItem  
 Создает новый список, содержащий два Pidl.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidl1`  
 Первый элемент.  
  
 [in] `pidl2`  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый список элементов, если функция выполняется успешно `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает новый [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) достаточно велик, чтобы содержать оба `pidl1` и `pidl2`. Затем копирует `pidl1` и `pidl2` в новый список.  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 Копирует список элементов.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidlSource`  
 Исходным списком элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный элемент списка, если выполнено успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Вновь созданный элемент списка имеет тот же размер элемента в списке.  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 Создает новый PIDL.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `cbSize`  
 Размер списка элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент списка, если выполнено успешно; в противном случае `NULL`.  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 Создает объект `CShellManager`.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не нужно создавать `CShellManager` напрямую. По умолчанию платформа создает его автоматически. Чтобы получить указатель на `CShellManager`, вызовите [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). При создании `CShellManager` вручную, его необходимо инициализировать с помощью метода [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 Удаляет список элементов.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidl`  
 Список элементов для удаления.  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 Возвращает количество элементов в списке элементов.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidl`  
 Указатель на список элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке элементов.  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 Возвращает размер списка элементов.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidl`  
 Указатель на список элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер списка элементов.  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 Получает следующий элемент из указателя в список идентификатор элемента (PIDL).  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pidl`  
 Список элементов для итерации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель к следующему элементу в списке.  
  
### <a name="remarks"></a>Примечания  
 Если в списке нет дополнительных элементов, этот метод возвращает `NULL`.  
  
##  <a name="getparentitem"></a>CShellManager::GetParentItem  
 Извлекает родительский указатель на идентификатор списка элементов (PIDL).  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpidl`  
 PIDL, будет получен, родительский объект.  
  
 [выходной] `lpidlParent`  
 Ссылка на PIDL, где метод будет храниться результат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уровень PIDL родительского элемента.  
  
### <a name="remarks"></a>Примечания  
 Уровень PIDL является относительно рабочего стола. Считается, что системная PIDL с уровнем 0.  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 Извлекает указатель на список идентификатор элемента (PIDL) из элемента, заданный с помощью строки пути.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPath`  
 Строка, указывающая путь к элементу.  
  
 [выходной] `pidl`  
 Ссылка на PIDL. Метод использует этот PIDL для хранения указателя для возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `NOERROR` Если выполнено успешно; значение ошибки, определенное OLE.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

