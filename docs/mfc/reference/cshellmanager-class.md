---
title: Класс CShellManager | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35f186822e00f74552e3bf8d52950f3c4bbe5b45
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207396"
---
# <a name="cshellmanager-class"></a>Класс CShellManager
Реализует несколько методов, которые позволяют работать с указателями в списках идентификаторов (PIDL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Создает объект `CShellManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Отображает диалоговое окно, которое позволяет пользователю выбрать папку оболочки.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Сцепляет два Pidl.|  
|[CShellManager::CopyItem](#copyitem)|Создает новый PIDL и копирует предоставленный PIDL к нему.|  
|[CShellManager::CreateItem](#createitem)|Создает новый PIDL указанного размера.|  
|[CShellManager::FreeItem](#freeitem)|Удаляет предоставленный PIDL.|  
|[CShellManager::GetItemCount](#getitemcount)|Возвращает количество элементов в предоставленный PIDL.|  
|[CShellManager::GetItemSize](#getitemsize)|Возвращает размер предоставленного PIDL.|  
|[CShellManager::GetNextItem](#getnextitem)|Возвращает следующий элемент из PIDL.|  
|[CShellManager::GetParentItem](#getparentitem)|Извлекает родительский элемент указанного элемента.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Извлекает PIDL для элемента, определяемого по указанному пути.|  
  
## <a name="remarks"></a>Примечания  
 Методы `CShellManager` класса все приходится иметь дело с Pidl. PIDL — это уникальный идентификатор для объекта оболочки.  
  
 Не следует создавать `CShellManager` объект вручную. Он будет создаваться автоматически платформой приложения. Тем не менее, следует вызывать [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) во время инициализации приложения. Чтобы получить указатель на диспетчер оболочки для вашего приложения, вызовите [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder  
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
 [out] *strOutFolder*  
 Строка, используемая этим методом для сохранения пути из выбранной папки.  
  
 [in] *pWndParent*  
 Указатель на родительское окно.  
  
 [in] *lplszInitialFolder*  
 Строка, содержащая папку, выбирается по умолчанию, когда появится диалоговое окно.  
  
 [in] *lpszTitle*  
 Заголовок для диалогового окна.  
  
 [in] *ulFlags*  
 Флаги, указывающие параметры для диалогового окна. См. в разделе [BROWSEINFO](/windows/desktop/api/shlobj_core/ns-shlobj_core-_browseinfoa) подробное описание.  
  
 [out] *piFolderImage*  
 Указатель на целочисленное значение, где метод записывает индекс изображения выбранной папки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь выбирает папки из диалогового окна; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 При вызове этого метода, приложение создает и отображает диалоговое окно, позволяющее пользователю выбрать папку. Метод запишет путь к папке в *strOutFolder* параметра.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как получить ссылку на `CShellManager` объекта с помощью `CWinAppEx::GetShellManager` метод и как использовать `BrowseForFolder` метод. Этот фрагмент кода является частью [пример Explorer](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem  
 Создает новый список, содержащий два Pidl.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidl1*  
 Первый элемент.  
  
 [in] *pidl2*  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый список элементов, если функция выполняется успешно, в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает новую [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) достаточно большим, чтобы вместить оба *pidl1* и *pidl2*. Затем он копирует *pidl1* и *pidl2* в новый список.  
  
##  <a name="copyitem"></a>  CShellManager::CopyItem  
 Копирует список элементов.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidlSource*  
 Исходным списками элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный элемент списка, если выполнение прошло успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Только что созданный элемент списка имеет тот же размер, в списке элементов.  
  
##  <a name="createitem"></a>  CShellManager::CreateItem  
 Создает новый PIDL.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *cbSize*  
 Размер в списке элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на созданный элемент списка, если выполнение прошло успешно; в противном случае имеет значение NULL.  
  
##  <a name="cshellmanager"></a>  CShellManager::CShellManager  
 Создает объект `CShellManager`.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не нужно создавать `CShellManager` напрямую. По умолчанию платформа создает ее автоматически. Чтобы получить указатель на `CShellManager`, вызовите [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Если вы создаете `CShellManager` вручную, необходимо инициализировать его с помощью метода [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>  CShellManager::FreeItem  
 Удаляет список элементов.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidl*  
 Список элементов для удаления.  
  
##  <a name="getitemcount"></a>  CShellManager::GetItemCount  
 Возвращает количество элементов в списке элементов.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidl*  
 Указатель на список элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке элементов.  
  
##  <a name="getitemsize"></a>  CShellManager::GetItemSize  
 Возвращает размер списка элементов.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidl*  
 Указатель на список элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в списке элементов.  
  
##  <a name="getnextitem"></a>  CShellManager::GetNextItem  
 Извлекает следующий элемент из указателя для элемента списка идентификаторов (PIDL).  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pidl*  
 Список элементов для итерации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий элемент в списке.  
  
### <a name="remarks"></a>Примечания  
 Если в списке больше нет элементов, этот метод возвращает значение NULL.  
  
##  <a name="getparentitem"></a>  CShellManager::GetParentItem  
 Извлекает родительский указатель на элемент списка идентификаторов (PIDL).  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpidl*  
 PIDL, родитель которого будут извлекаться.  
  
 [out] *lpidlParent*  
 Ссылка на PIDL, где метод сохранит результат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уровень PIDL родительского элемента.  
  
### <a name="remarks"></a>Примечания  
 Уровень PIDL задается относительно рабочего стола. Уровень 0 считается PIDL рабочего стола.  
  
##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath  
 Извлекает указатель на элемент списка идентификаторов (PIDL) из элемента, заданный с помощью строки пути.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszPath*  
 Строковое значение, указывающее путь для элемента.  
  
 [out] *pidl*  
 Ссылка на PIDL. Данный метод использует этот PIDL для хранения указателя на его возвращаемое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение NOERROR, если выполнение прошло успешно; значение ошибки, определенное OLE.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
