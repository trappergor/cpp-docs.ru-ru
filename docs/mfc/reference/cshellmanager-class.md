---
title: Класс Кшеллманажер
ms.date: 11/04/2016
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
ms.openlocfilehash: 8151550dafdd1bdf8593d555008af387cf548bc8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502619"
---
# <a name="cshellmanager-class"></a>Класс Кшеллманажер

Реализует несколько методов, которые позволяют работать с указателями в списках идентификаторов (PIDL).

## <a name="syntax"></a>Синтаксис

```
class CShellManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кшеллманажер:: Кшеллманажер](#cshellmanager)|Создает объект `CShellManager`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кшеллманажер:: Бровсефорфолдер](#browseforfolder)|Отображает диалоговое окно, позволяющее пользователю выбрать папку оболочки.|
|[Кшеллманажер:: Конкатенатеитем](#concatenateitem)|Сцепляет два PIDL.|
|[Кшеллманажер:: CopyItem](#copyitem)|Создает новый ПИДЛ и копирует в него указанный ПИДЛ.|
|[Кшеллманажер:: CreateItem](#createitem)|Создает новый ПИДЛ указанного размера.|
|[Кшеллманажер:: Фриитем](#freeitem)|Удаляет указанный ПИДЛ.|
|[CShellManager::GetItemCount](#getitemcount)|Возвращает количество элементов в заданном ПИДЛ.|
|[Кшеллманажер:: Жетитемсизе](#getitemsize)|Возвращает размер заданного ПИДЛ.|
|[CShellManager::GetNextItem](#getnextitem)|Возвращает следующий элемент из ПИДЛ.|
|[Кшеллманажер:: Жетпарентитем](#getparentitem)|Извлекает родительский элемент заданного элемента.|
|[CShellManager::ItemFromPath](#itemfrompath)|Получает ПИДЛ для элемента, определяемого указанным путем.|

## <a name="remarks"></a>Примечания

Методы `CShellManager` класса работают с PIDL. ПИДЛ — это уникальный идентификатор для объекта Shell.

Не следует создавать `CShellManager` объект вручную. Он будет создан автоматически платформой приложения. Однако в процессе инициализации приложения следует вызвать [CWinAppEx:: инитшеллманажер](../../mfc/reference/cwinappex-class.md#initshellmanager) . Чтобы получить указатель на диспетчер оболочки для своего приложения, вызовите [CWinAppEx:: жетшеллманажер](../../mfc/reference/cwinappex-class.md#getshellmanager).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кшеллманажер](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксшеллманажер. h

##  <a name="browseforfolder"></a>Кшеллманажер:: Бровсефорфолдер

Отображает диалоговое окно, позволяющее пользователю выбрать папку оболочки.

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

*страутфолдер*<br/>
заполняет Строка, используемая методом для хранения пути к выбранной папке.

*пвндпарент*<br/>
окне Указатель на родительское окно.

*лплсзинитиалфолдер*<br/>
окне Строка, содержащая папку, выбранную по умолчанию при отображении диалогового окна.

*лпсзтитле*<br/>
окне Заголовок для диалогового окна.

*улфлагс*<br/>
окне Флаги, указывающие параметры для диалогового окна. Подробное описание см. в разделе [бровсеинфо](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow) .

*пифолдеримаже*<br/>
заполняет Указатель на целочисленное значение, в котором метод записывает индекс изображения выбранной папки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь выбирает папку из диалогового окна; в противном случае — 0.

### <a name="remarks"></a>Примечания

При вызове этого метода приложение создает и отображает диалоговое окно, позволяющее пользователю выбрать папку. Метод запишет путь к папке в параметр *страутфолдер* .

### <a name="example"></a>Пример

В следующем примере показано, как получить ссылку на `CShellManager` объект с `CWinAppEx::GetShellManager` помощью метода `BrowseForFolder` и как использовать метод. Этот фрагмент кода является частью [примера обозревателя](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

##  <a name="concatenateitem"></a>Кшеллманажер:: Конкатенатеитем

Создает новый список, содержащий два PIDL.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>Параметры

*pidl1*<br/>
окне Первый элемент.

*pidl2*<br/>
окне Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый список элементов, если функция выполнена, в противном случае — NULL.

### <a name="remarks"></a>Примечания

Этот метод создает новый [итемидлист](/windows/win32/api/shtypes/ns-shtypes-itemidlist) , достаточно большой для размещения как *pidl1* , так и *pidl2*. Затем он копирует *pidl1* и *pidl2* в новый список.

##  <a name="copyitem"></a>Кшеллманажер:: CopyItem

Копирует список элементов.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>Параметры

*пидлсаурце*<br/>
окне Исходный список элементов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный список элементов в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Созданный список элементов имеет тот же размер, что и исходный список элементов.

##  <a name="createitem"></a>Кшеллманажер:: CreateItem

Создает новый ПИДЛ.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>Параметры

*кбсизе*<br/>
окне Размер списка элементов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на созданный список элементов в случае успеха; в противном случае — NULL.

##  <a name="cshellmanager"></a>Кшеллманажер:: Кшеллманажер

Создает объект `CShellManager`.

```
CShellManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев нет необходимости создавать `CShellManager` напрямую. По умолчанию платформа создает ее. Чтобы получить указатель `CShellManager`на, вызовите метод [CWinAppEx:: жетшеллманажер](../../mfc/reference/cwinappex-class.md#getshellmanager). Если создать `CShellManager` вручную, необходимо инициализировать его с помощью метода [CWinAppEx:: инитшеллманажер](../../mfc/reference/cwinappex-class.md#initshellmanager).

##  <a name="freeitem"></a>Кшеллманажер:: Фриитем

Удаляет список элементов.

```
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*пидл*<br/>
окне Список элементов для удаления.

##  <a name="getitemcount"></a>Кшеллманажер:: GetItemCount

Возвращает число элементов в списке элементов.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*пидл*<br/>
окне Указатель на список элементов.

### <a name="return-value"></a>Возвращаемое значение

Число элементов в списке элементов.

##  <a name="getitemsize"></a>Кшеллманажер:: Жетитемсизе

Возвращает размер списка элементов.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*пидл*<br/>
окне Указатель на список элементов.

### <a name="return-value"></a>Возвращаемое значение

Размер списка элементов.

##  <a name="getnextitem"></a>  CShellManager::GetNextItem

Извлекает следующий элемент из указателя на список идентификаторов элементов (ПИДЛ).

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*пидл*<br/>
окне Список элементов для итерации.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент в списке.

### <a name="remarks"></a>Примечания

Если в списке больше нет элементов, этот метод возвращает значение NULL.

##  <a name="getparentitem"></a>Кшеллманажер:: Жетпарентитем

Возвращает родительский объект указателя на список идентификаторов элементов (ПИДЛ).

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>Параметры

*лпидл*<br/>
окне Объект ПИДЛ, родительский элемент которого будет извлечен.

*лпидлпарент*<br/>
заполняет Ссылка на ПИДЛ, где метод будет хранить результат.

### <a name="return-value"></a>Возвращаемое значение

Уровень родительского ПИДЛ.

### <a name="remarks"></a>Примечания

Уровень ПИДЛа относится к рабочему столу. Настольная ПИДЛ считается уровнем 0.

##  <a name="itemfrompath"></a>Кшеллманажер:: Итемфромпас

Получает указатель на список идентификаторов элементов (ПИДЛ) из элемента, определяемого по строковому пути.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>Параметры

*лпсзпас*<br/>
окне Строка, указывающая путь для элемента.

*пидл*<br/>
заполняет Ссылка на ПИДЛ. Метод использует этот ПИДЛ для сохранения указателя на возвращаемое значение.

### <a name="return-value"></a>Возвращаемое значение

При успешном выполнении возвращает ошибку. значение ошибки, определенное OLE.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
