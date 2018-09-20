---
title: Класс CMonikerFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 977bf0a56e21ddbef62daf88a7aa459d7c275a99
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405253"
---
# <a name="cmonikerfile-class"></a>Класс CMonikerFile

Представляет поток данных ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)) с именем, [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker).

## <a name="syntax"></a>Синтаксис

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Создает объект `CMonikerFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::Close](#close)|Отсоединяет и освобождает поток и освобождает моникер.|
|[CMonikerFile::Detach](#detach)|Отсоединяет `IMoniker` из этого `CMonikerFile` объекта.|
|[CMonikerFile::GetMoniker](#getmoniker)|Возвращает текущий моникер.|
|[CMonikerFile::Open](#open)|Открывает указанный файл для получения потока.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|Получает контекст привязки, или создает контекст привязки по умолчанию.|

## <a name="remarks"></a>Примечания

Моникер содержит сведения, как путь к файлу. Если у вас есть указатель на объект моникера `IMoniker` интерфейс, можно получить доступ к файлу, определенный без необходимости другие определенные сведения о расположении файла фактически.

Является производным от `COleStreamFile`, `CMonikerFile` принимает моникер или строковое представление, его можно преобразовать в моникер и привязывает к потоку, для которого моникер — это имя. Кроме того, можно затем чтение и запись в поток. Настоящая цель `CMonikerFile` — предоставить простой доступ к `IStream`s с именем, `IMoniker`s, чтобы у вас нет для привязки к потоку, еще нет `CFile` функциональные возможности в поток.

`CMonikerFile` не может использоваться для привязки к отличным от потока. Если вы хотите выполнить привязку в хранилище или объекта, необходимо использовать `IMoniker` взаимодействует напрямую.

Дополнительные сведения о потоках и моникеров, см. в разделе [COleStreamFile](../../mfc/reference/colestreamfile-class.md) в *Справочник по библиотеке MFC* и [IStream](/windows/desktop/api/objidl/nn-objidl-istream) и [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="close"></a>  CMonikerFile::Close

Вызывайте эту функцию для выделения и освобождения потока и освободить моникер.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Может вызываться в потоках неоткрытый или уже закрыт.

##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile

Создает объект `CMonikerFile`.

```
CMonikerFile();
```

##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext

Вызывайте эту функцию для создания контекста привязки по умолчанию.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Параметры

*pError*<br/>
Указатель на исключение файлов. В случае ошибки он устанавливается на причину.

### <a name="return-value"></a>Возвращаемое значение

Указатель на контекст привязки [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) для привязки с, если успешно; в противном случае — NULL. Если экземпляр был открыт с помощью `IBindHost` интерфейс, контекст привязки, извлекается из `IBindHost`. Если нет `IBindHost` интерфейс или не возвращает контекст привязки, создается контекст привязки. Описание [IBindHost](https://msdn.microsoft.com/library/ie/ms775076) интерфейсом, см. в Windows SDK.

### <a name="remarks"></a>Примечания

Контекст привязки — это объект, который хранит сведения об операциях привязки к конкретной моникер. Можно переопределить эту функцию для предоставления контекста пользовательские привязки.

##  <a name="detach"></a>  CMonikerFile::Detach

Вызывайте эту функцию, чтобы закрыть поток.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*pError*<br/>
Указатель на исключение файлов. В случае ошибки он устанавливается на причину.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker

Вызывайте эту функцию для получения указателя на текущий моникер.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий моникер интерфейс ( [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)).

### <a name="remarks"></a>Примечания

Так как `CMonikerFile` не является интерфейсом, возвращенный указатель не увеличивает счетчик ссылок (через [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)), и моникер освобождается при `CMonikerFile` объект освобождается. Если вы хотите удержать моникер или освободите его самостоятельно, вы должны `AddRef` его.

##  <a name="open"></a>  CMonikerFile::Open

Вызов этой функции-члена для открытия файла или моникер объекта.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);


virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
URL-адрес или имя открываемого файла.

*pError*<br/>
Указатель на исключение файлов. В случае ошибки он устанавливается на причину.

*pMoniker*<br/>
Указатель на интерфейс моникер `IMoniker` использоваться для получения потока.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

*LpszURL* параметр нельзя использовать на компьютерах Macintosh. Только *pMoniker* форме `Open` может использоваться на компьютерах Macintosh.

Можно использовать URL-адрес или имя файла для *lpszURL* параметра. Пример:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- или -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>См. также

[Класс COleStreamFile](../../mfc/reference/colestreamfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
