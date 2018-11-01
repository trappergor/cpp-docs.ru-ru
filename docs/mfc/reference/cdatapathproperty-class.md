---
title: Класс CDataPathProperty
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 1d17b121854623e9919f434a44b6ab40c2db2691
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608190"
---
# <a name="cdatapathproperty-class"></a>Класс CDataPathProperty

Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

## <a name="syntax"></a>Синтаксис

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Создает объект `CDataPathProperty`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDataPathProperty::GetControl](#getcontrol)|Извлекает асинхронной управления OLE, связанный с `CDataPathProperty` объекта.|
|[CDataPathProperty::GetPath](#getpath)|Получает путь свойства.|
|[CDataPathProperty::Open](#open)|Инициирует загрузку асинхронного свойства связанного элемента управления ActiveX (OLE).|
|[CDataPathProperty::ResetData](#resetdata)|Вызовы `CAsyncMonikerFile::OnDataAvailable` для уведомления контейнер, в котором изменились свойства элемента управления.|
|[CDataPathProperty::SetControl](#setcontrol)|Задает асинхронный элемент управления ActiveX (OLE), связанный со свойством.|
|[CDataPathProperty::SetPath](#setpath)|Задает путь к свойству.|

## <a name="remarks"></a>Примечания

Асинхронные свойства загружаются после синхронного запуска.

Класс `CDataPathProperty` является производным от `CAysncMonikerFile`. Для реализации асинхронных свойств элементов управления OLE, наследуйте класс от `CDataPathProperty`и Переопределите [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).

Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в разделе со следующими статьями:

- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty

Создает объект `CDataPathProperty`.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на элемент управления OLE-объекта должны быть сопоставлены это `CDataPathProperty` объекта.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного моникера, который ссылается на фактическое расположение абсолютный свойства. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите, чтобы `CDataPathProperty` объекта для файла, добавить в начало `file://` к пути.

### <a name="remarks"></a>Примечания

`COleControl` Объекта, на который указывает *pControl* используется `Open` и получить производными классами. Если *pControl* имеет значение NULL, элемент управления, используемый с `Open` следует задавать с `SetControl`. Если *lpszPath* имеет значение NULL, можно передать путь через `Open` или установка его с помощью `SetPath`.

##  <a name="getcontrol"></a>  CDataPathProperty::GetControl

Вызовите эту функцию-член для извлечения `COleControl` объект, связанный с `CDataPathProperty` объекта.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на элемент управления OLE, связанный с `CDataPathProperty` объекта. Значение NULL, если нет элемента управления связан.

##  <a name="getpath"></a>  CDataPathProperty::GetPath

Вызовите эту функцию-член для извлечения путь, устанавливается, когда `CDataPathProperty` объект был создан, или указать в `Open`, или указанный в предыдущем вызове `SetPath` функция-член.

```
CString GetPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает путь к самому свойству. Может быть пустым, если путь не был указан.

##  <a name="open"></a>  CDataPathProperty::Open

Вызовите эту функцию-член инициировать загрузку асинхронного свойства связанного элемента управления.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на элемент управления OLE-объекта должны быть сопоставлены это `CDataPathProperty` объекта.

*pError*<br/>
Указатель на исключение файлов. В случае ошибки будут устанавливаться на причину.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного моникера, который ссылается на фактическое расположение абсолютный свойства. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите, чтобы `CDataPathProperty` объекта для файла, добавить в начало `file://` к пути.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Функция пытается получить `IBindHost` интерфейса из элемента управления.

Перед вызовом `Open` без пути, необходимо задать значение для свойства пути. Это можно сделать, если объект является сконструированный, или путем вызова `SetPath` функция-член.

Перед вызовом `Open` без элемента управления, элемент управления ActiveX (прежнее название элемента управления OLE) может быть связан с объектом. Это можно сделать, если объект является сконструированный, или путем вызова `SetControl`.

Все перегрузки [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) также доступны из `CDataPathProperty`.

##  <a name="resetdata"></a>  CDataPathProperty::ResetData

Вызовите эту функцию для получения `CAsyncMonikerFile::OnDataAvailable` для уведомления в контейнер, изменились свойства элемента управления, что все сведения, загружен в асинхронном режиме не используется.

```
virtual void ResetData();
```

### <a name="remarks"></a>Примечания

Открытие должна быть перезапущена. Производные классы могут переопределять эту функцию для различные значения по умолчанию.

##  <a name="setcontrol"></a>  CDataPathProperty::SetControl

Вызовите эту функцию-член для связи с асинхронной управления OLE `CDataPathProperty` объекта.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на асинхронных управления OLE, связываемое со свойством.

##  <a name="setpath"></a>  CDataPathProperty::SetPath

Эта функция члена для задания пути свойства.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным к свойству, загружаемого в асинхронном режиме. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите, чтобы `CDataPathProperty` объекта для файла, добавить в начало `file://` к пути.

## <a name="see-also"></a>См. также

[Пример MFC изображения](../../visual-cpp-samples.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
