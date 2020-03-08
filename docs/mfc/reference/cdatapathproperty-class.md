---
title: Класс Кдатапаспроперти
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
ms.openlocfilehash: 89cb8ddcdd42643f52f755516e8845109163c57a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890828"
---
# <a name="cdatapathproperty-class"></a>Класс Кдатапаспроперти

Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

## <a name="syntax"></a>Синтаксис

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кдатапаспроперти:: Кдатапаспроперти](#cdatapathproperty)|Формирует объект `CDataPathProperty`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кдатапаспроперти:: oncontrol](#getcontrol)|Извлекает асинхронный элемент управления OLE, связанный с объектом `CDataPathProperty`.|
|[Кдатапаспроперти:: path](#getpath)|Извлекает путь к свойству.|
|[Кдатапаспроперти:: Open](#open)|Инициирует загрузку асинхронного свойства для связанного элемента управления ActiveX (OLE).|
|[Кдатапаспроперти:: Ресетдата](#resetdata)|Вызывает `CAsyncMonikerFile::OnDataAvailable`, чтобы уведомить контейнер об изменении свойств элемента управления.|
|[Кдатапаспроперти:: Сетконтрол](#setcontrol)|Задает асинхронный элемент управления ActiveX (OLE), связанный со свойством.|
|[Кдатапаспроперти:: Сетпас](#setpath)|Задает путь к свойству.|

## <a name="remarks"></a>Remarks

Асинхронные свойства загружаются после синхронной инициации.

Класс `CDataPathProperty` является производным от `CAysncMonikerFile`. Чтобы реализовать асинхронные свойства в элементах управления OLE, создайте класс на основе `CDataPathProperty`и переопределите [ондатааваилабле](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).

Дополнительные сведения об использовании асинхронных моникеров и элементов управления ActiveX в веб – приложениях см. в следующих статьях:

- [Первые действия в Интернете: элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Первые действия через Интернет: асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кфиле](../../mfc/reference/cfile-class.md)

[колестреамфиле](../../mfc/reference/colestreamfile-class.md)

[кмоникерфиле](../../mfc/reference/cmonikerfile-class.md)

[касинкмоникерфиле](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl. h

##  <a name="cdatapathproperty"></a>Кдатапаспроперти:: Кдатапаспроперти

Формирует объект `CDataPathProperty`.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Параметры

*пконтрол*<br/>
Указатель на управляющий объект OLE, связываемый с данным объектом `CDataPathProperty`.

*лпсзпас*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного моникера, который ссылается на фактическое абсолютное расположение свойства. `CDataPathProperty` использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, в начале `file://` путь.

### <a name="remarks"></a>Remarks

Объект `COleControl`, на который указывает *пконтрол* , используется `Open` и извлекается производными классами. Если *пконтрол* имеет значение null, то элемент управления, используемый с `Open`, должен быть установлен в `SetControl`. Если *лпсзпас* имеет значение null, можно передать путь через `Open` или задать его с помощью `SetPath`.

##  <a name="getcontrol"></a>Кдатапаспроперти:: oncontrol

Вызовите эту функцию члена, чтобы получить объект `COleControl`, связанный с объектом `CDataPathProperty`.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на элемент управления OLE, связанный с объектом `CDataPathProperty`. Значение NULL, если элемент управления не связан.

##  <a name="getpath"></a>Кдатапаспроперти:: path

Вызовите эту функцию-член, чтобы получить путь, задать, когда `CDataPathProperty` объект был создан или указан в `Open`или указан в предыдущем вызове функции-члена `SetPath`.

```
CString GetPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает путь к самому свойству. Может быть пустым, если путь не указан.

##  <a name="open"></a>Кдатапаспроперти:: Open

Вызовите эту функцию члена, чтобы инициировать загрузку асинхронного свойства для связанного элемента управления.

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

*пконтрол*<br/>
Указатель на управляющий объект OLE, связываемый с данным объектом `CDataPathProperty`.

*pError*<br/>
Указатель на исключение файла. В случае ошибки будет задана причина.

*лпсзпас*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного моникера, который ссылается на фактическое абсолютное расположение свойства. `CDataPathProperty` использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, в начале `file://` путь.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Функция пытается получить интерфейс `IBindHost` из элемента управления.

Перед вызовом `Open` без пути необходимо задать значение для пути к свойству. Это можно сделать при создании объекта или путем вызова функции-члена `SetPath`.

Перед вызовом `Open` без элемента управления элемент управления ActiveX (прежнее название — элемент управления OLE) может быть связан с объектом. Это можно сделать при создании объекта или путем вызова `SetControl`.

Все перегрузки [касинкмоникерфиле:: Open](../../mfc/reference/casyncmonikerfile-class.md#open) также доступны из `CDataPathProperty`.

##  <a name="resetdata"></a>Кдатапаспроперти:: Ресетдата

Вызовите эту функцию, чтобы получить `CAsyncMonikerFile::OnDataAvailable` уведомлять контейнер об изменении свойств элемента управления, и вся информация, загруженная асинхронно, больше не полезна.

```
virtual void ResetData();
```

### <a name="remarks"></a>Remarks

Необходимо перезапустить открытие. Производные классы могут переопределять эту функцию для различных значений по умолчанию.

##  <a name="setcontrol"></a>Кдатапаспроперти:: Сетконтрол

Вызовите эту функцию члена, чтобы связать асинхронный элемент управления OLE с объектом `CDataPathProperty`.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Параметры

*пконтрол*<br/>
Указатель на асинхронный элемент управления OLE, который должен быть связан со свойством.

##  <a name="setpath"></a>Кдатапаспроперти:: Сетпас

Вызовите эту функцию члена, чтобы задать путь к свойству.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Параметры

*лпсзпас*<br/>
Путь, который может быть абсолютным или относительным для свойства, загружаемого асинхронно. `CDataPathProperty` использует URL-адреса, а не имена файлов. Если требуется `CDataPathProperty` объект для файла, в начале `file://` путь.

## <a name="see-also"></a>См. также раздел

[Пример изображения MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
