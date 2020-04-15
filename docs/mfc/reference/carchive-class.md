---
title: Класс CArchive
ms.date: 11/04/2016
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
ms.openlocfilehash: 46d30e38674d10aecdfdbf7be91c48063ba9f493
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377067"
---
# <a name="carchive-class"></a>Класс CArchive

Позволяет сохранить сложную сеть объектов в постоянной двоичной форме (обычно хранении дисков), которая сохраняется после удаления этих объектов.

## <a name="syntax"></a>Синтаксис

```
class CArchive
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|Создает объект `CArchive`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CArchive::Аборт](#abort)|Закрывает архив, не выбрасывая исключения.|
|[CArchive::Закрыть](#close)|Сбрасывает неписаные данные и `CFile`отключается от .|
|[CArchive::Флеш](#flush)|Сбрасывает неписаные данные из буфера архива.|
|[CArchive::GetFile](#getfile)|Получает `CFile` указатель объекта для этого архива.|
|[CArchive::GetObjectSchema](#getobjectschema)|Вызывается `Serialize` из функции для определения версии объекта, который в настоящее время десериалифицируется.|
|[CArchive::IsBufferEmpty](#isbufferempty)|Определяет, был ли буфер опорожнен во время процесса получения розеток Windows.|
|[CArchive::Загрузка](#isloading)|Определяет, загружается ли архив.|
|[CArchive::Istoring](#isstoring)|Определяет, хранится ли архив.|
|[CArchive::MapObject](#mapobject)|Места объектов на карте, которые не сериализованы для файла, но которые доступны для субобъектов для ссылки.|
|[CArchive::Читать](#read)|Читает сырые байты.|
|[CArchive::ReadClass](#readclass)|Читает ссылку класса, `WriteClass`ранее хранящуюся с .|
|[CArchive::ReadObject](#readobject)|Вызывает функцию `Serialize` объекта для загрузки.|
|[CArchive::ReadString](#readstring)|Читает одну строку текста.|
|[CArchive::SerializeClass](#serializeclass)|Читает или пишет ссылку `CArchive` класса на объект в `CArchive`зависимости от направления .|
|[CArchive::SetLoadParams](#setloadparams)|Устанавливает размер, к которому растет массив нагрузки. Необходимо вызвать до того, как `MapObject` `ReadObject` какой-либо объект будет загружен или до или вызван.|
|[CArchive::SetObjectSchema](#setobjectschema)|Устанавливает схему объекта, хранящуюся в объекте архива.|
|[CArchive::SetStoreParams](#setstoreparams)|Устанавливает размер таблицы хэша и размер блока карты, используемой для идентификации уникальных объектов в процессе сериализации.|
|[CArchive::Запись](#write)|Пишет сырые байты.|
|[CArchive::WriteClass](#writeclass)|Пишет ссылку `CRuntimeClass` на `CArchive`.|
|[CArchive::WriteObject](#writeobject)|Вызывает `Serialize` функцию объекта для хранения.|
|[CArchive::WriteString](#writestring)|Пишет одну строку текста.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CArchive::оператор&lt;&lt;](#operator_lt_lt)|Хранит объекты и примитивные типы в архиве.|
|[CArchive::оператор&gt;&gt;](#operator_gt_gt)|Загружает объекты и примитивные типы из архива.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Remarks

`CArchive`не имеет базового класса.

Позже можно загрузить объекты из постоянного хранилища, восставив их в памяти. Этот процесс обеспечения настойчивости данных называется «сериализация».

Объект архива можно считать своего рода двоичным потоком. Как и поток ввода/вывода, архив связан с файлом и позволяет буферизированное письмо и чтение данных в хранилище и из его. Поток ввода/вывода обрабатывает последовательности символов ASCII, но архив обрабатывает данные двоичных объектов в эффективном, неисчерпаемом формате.

Прежде чем [CFile](../../mfc/reference/cfile-class.md) можно создать `CArchive` объект. Кроме того, необходимо убедиться, что состояние загрузки/хранилища архива совместимо с открытым режимом файла. Вы ограничены одним активным архивом на файл.

При построении `CArchive` объекта его прикрепляют `CFile` к объекту класса (или производным классам), который представляет собой открытый файл. Вы также указываете, будет ли архив использоваться для загрузки или хранения. Объект `CArchive` может обрабатывать не только примитивные типы, но и объекты классов [CObject,](../../mfc/reference/cobject-class.md)предназначенных для сериализации. Сериализируемый класс обычно `Serialize` имеет функцию члена, и он обычно использует [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макросов, как описано в классе. `CObject`

Перегруженное извлечение () **>>** и **<<** вставка () операторы являются удобными `CObject`интерфейсами архивного программирования, которые поддерживают как примитивные типы, так и -производные классы.

`CArchive`также поддерживает программирование с MFC Windows Розетки классов [CSocket](../../mfc/reference/csocket-class.md) и [CSocketFile](../../mfc/reference/csocketfile-class.md). Функция члена [IsBufferEmpty](#isbufferempty) поддерживает это использование.

Для получения `CArchive`дополнительной информации о , см. статьи [Сериализация](../../mfc/serialization-in-mfc.md) и [Windows розетки: Использование розетки с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CArchive`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="carchiveabort"></a><a name="abort"></a>CArchive::Аборт

Вызовите эту функцию, чтобы закрыть архив, не бросая исключения.

```
void Abort ();
```

### <a name="remarks"></a>Remarks

Деструктор `CArchive` обычно вызывает `Close`вызов, который будет смывать любые `CFile` данные, которые не были сохранены для связанного объекта. Это может привести к исключениям.

При ловле этих исключений рекомендуется `Abort`использовать, чтобы уничтожение `CArchive` объекта не вызывало дальнейших исключений. При обработке `CArchive::Abort` исключений, не будет бросать исключение на сбои, потому что, в отличие от [CArchive::Закрыть](#close), `Abort` игнорирует сбои.

Если вы использовали **новый** для выделения `CArchive` объекта на куче, то вы должны удалить его после закрытия файла.

### <a name="example"></a>Пример

  Смотрите пример [CArchive::WriteClass](#writeclass).

## <a name="carchivecarchive"></a><a name="carchive"></a>CArchive::CArchive

Строит `CArchive` объект и определяет, будет ли он использоваться для загрузки или хранения объектов.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на `CFile` объект, который является конечным источником или пунктом назначения стойких данных.

*nMode*<br/>
Флаг, который определяет, будут ли объекты загружены из архива или сохранены. Параметр *nMode* должен иметь одно из следующих значений:

- `CArchive::load`Загружает данные из архива. Требуется `CFile` только разрешение на чтение.

- `CArchive::store`Сохраняет данные в архиве. Требуется `CFile` разрешение на запись.

- `CArchive::bNoFlushOnDelete`Предотвращает автоматическое вызов `Flush` архива при вызове деструктора архива. Если вы установите этот флаг, вы `Close` несете ответственность за явное вызов до того, как будет назван деструктор. Если вы этого не сделаете, ваши данные будут повреждены.

*nBufSize*<br/>
Масштаб, опосредуемый размер внутреннего буфера файла, в байтах. Обратите внимание, что размер буфера по умолчанию составляет 4096 байтов. Если вы регулярно архивируете крупные объекты, вы улучшите производительность, если вы используете больший размер буфера, который является кратным размеру буфера файла.

*lpBuf*<br/>
Дополнительный указатель на пользовательский буфер размера *nBufSize.* Если вы не укажете этот параметр, архив выделяет буфер из локальной кучи и освобождает его при уничтожении объекта. Архив не освобождает буфер, поставляемый пользователем.

### <a name="remarks"></a>Remarks

Вы не можете изменить эту спецификацию после создания архива.

Операции не `CFile` могут использоваться для изменения состояния файла до тех пор, пока не закроем архив. Любая такая операция нанесет ущерб целостности архива. Вы можете получить доступ к позиции указателя файла в любое время во время сериализации, получив файловый объект архива из функции члена [GetFile,](#getfile) а затем используя функцию [CFile::GetPosition.](../../mfc/reference/cfile-class.md#getposition) Вы должны позвонить [CArchive::Flush](#flush) до получения позиции указателя файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

## <a name="carchiveclose"></a><a name="close"></a>CArchive::Закрыть

Сбрасывает все данные, оставшиеся в буфере, закрывает архив и отключает архив из файла.

```
void Close();
```

### <a name="remarks"></a>Remarks

Дальнейшие операции в архиве не допускаются. После закрытия архива можно создать другой архив для того же файла или закрыть файл.

Функция `Close` участника гарантирует, что все данные будут переданы из архива в файл, и это делает архив недоступным. Для завершения передачи из файла в среду хранения необходимо сначала использовать [CFile:::Закрыть,](../../mfc/reference/cfile-class.md#close) а затем уничтожить `CFile` объект.

### <a name="example"></a>Пример

  Смотрите пример для [CArchive::WriteString](#writestring).

## <a name="carchiveflush"></a><a name="flush"></a>CArchive::Флеш

Принудя любые данные, оставшиеся в буфере архива, к написанию файла.

```
void Flush();
```

### <a name="remarks"></a>Remarks

Функция `Flush` участника гарантирует передачу всех данных из архива в файл. Вы должны вызвать [CFile::Близко для](../../mfc/reference/cfile-class.md#close) завершения передачи из файла в среду хранения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

## <a name="carchivegetfile"></a><a name="getfile"></a>CArchive::GetFile

Получает `CFile` указатель объекта для этого архива.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Постоянная указка `CFile` на объект, накоторыйумый на объект.

### <a name="remarks"></a>Remarks

Вы должны промыть `GetFile`архив перед использованием .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

## <a name="carchivegetobjectschema"></a><a name="getobjectschema"></a>CArchive::GetObjectSchema

Вызов исчергить эту функцию из функции, `Serialize` чтобы определить версию объекта, который в настоящее время десериалифицируется.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Возвращаемое значение

Во время десериализации версия объекта читается.

### <a name="remarks"></a>Remarks

Вызов этой функции действителен только при загрузке `CArchive` объекта [(CArchive::IsLoading](#isloading) возвращается ненулевой). Это должен быть первый `Serialize` вызов в функции и вызов только один раз. Значение возврата (UINT)-1 указывает на то, что номер версии неизвестен.

Класс `CObject`A-derived может использовать VERSIONABLE_SCHEMA комбинированные (с помощью bitwise **OR)** с самой версией схемы (в IMPLEMENT_SERIAL `Serialize` макрос) для создания "версионируемого объекта", т.е. объекта, функция члена которого может читать несколько версий. Функциональность платформы по умолчанию (без VERSIONABLE_SCHEMA) заключается в том, чтобы выбросить исключение, когда версия несовместима.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

## <a name="carchiveisbufferempty"></a><a name="isbufferempty"></a>CArchive::IsBufferEmpty

Вызовите эту функцию участника, чтобы определить, пуст внутренний буфер объекта архива.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если буфер архива пуст; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция поставляется для поддержки программирования с `CSocketFile`классом MFC Windows Sockets. Вам не нужно использовать его для архива, связанного с объектом. `CFile`

Причина использования `IsBufferEmpty` архива, связанного `CSocketFile` с объектом, заключается в том, что буфер архива может содержать несколько сообщений или записей. После получения одного сообщения `IsBufferEmpty` следует использовать для управления циклом, который продолжает получать данные до тех пор, пока буфер не будет пуст. Для получения дополнительной информации см. функцию участника `IsBufferEmpty` [Receive](../../mfc/reference/casyncsocket-class.md#receive) класса, `CAsyncSocket`которая показывает, как использовать .

Для получения дополнительной информации [см.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="carchiveisloading"></a><a name="isloading"></a>CArchive::Загрузка

Определяет, загружает ли архив данные.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если архив в настоящее время используется для загрузки; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается `Serialize` функциями архивных классов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

## <a name="carchiveisstoring"></a><a name="isstoring"></a>CArchive::Istoring

Определяет, хранит ли архив данные.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если архив в настоящее время используется для хранения; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается `Serialize` функциями архивных классов.

Если `IsStoring` статус архива незеровый, то его `IsLoading` статус 0, и наоборот.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

## <a name="carchivemapobject"></a><a name="mapobject"></a>CArchive::MapObject

Вызовите эту функцию участника для размещения объектов на карте, которые на самом деле не сериализованы в файл, но которые доступны для субобъектов для ссылки.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Параметры

*Тн*<br/>
Постоянная указка на сохраненный объект.

### <a name="remarks"></a>Remarks

Например, можно не сериализировать документ, но можно выписать элементы, которые являются частью документа. Позвонив, `MapObject`вы разрешаете этим элементам или субобъектам ссылаться на документ. Кроме того, серийные подпункты могут сериализировать свои *m_pDocument* указатель.

Вы можете `MapObject` звонить при хранении `CArchive` и загружать его. `MapObject`добавляет указанный объект в внутренние `CArchive` структуры данных, поддерживаемые объектом во время сериализации и десериализации, но в отличие от [ReadObject](#readobject) и [WriteObject,](#writeobject)он не вызывает сериализацию на объекте.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

## <a name="carchivem_pdocument"></a><a name="m_pdocument"></a>CArchive::m_pDocument

Установить в NULL по умолчанию, этот указатель `CDocument` на `CArchive` может быть установлен на все, что пользователь экземпляра хочет.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Remarks

Общее использование этого указателя заключается в передаче дополнительной информации о процессе сериализации всем объектам, которые сериализуются. Это достигается путем инициализации `CDocument`указателя с документом (классом производного), который сериализируется, таким образом, что объекты в документе могут получить доступ к документу в случае необходимости. Этот указатель также `COleClientItem` используется объектами во время сериализации.

Рамки устанавливают *m_pDocument* к сериализации документа, когда пользователь выдает команду File Open или Сохранить. При выпуске контейнерного документа Object Linking and Embedding (OLE) по причинам, не являющимся файлом Open или Save, необходимо четко установить *m_pDocument.* Например, это можно сделать при сериализации контейнерного документа в Clipboard.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

## <a name="carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a>CArchive::оператор&lt;&lt;

Хранит указанный объект или примитивный тип в архиве.

```
friend CArchive& operator<<(
    CArchive& ar,
    const CObject* pOb);

throw(
    CArchiveException*,
    CFileException*);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator<<(BYTE by);
CArchive& operator<<(WORD w);
CArchive& operator<<(LONG l);
CArchive& operator<<(DWORD dw);
CArchive& operator<<(float f);
CArchive& operator<<(double d);
CArchive& operator<<(int i);
CArchive& operator<<(short w);
CArchive& operator<<(char ch);
CArchive& operator<<(wchar_t ch);
CArchive& operator<<(unsigned u);
CArchive& operator<<(bool b);
CArchive& operator<<(ULONGLONG dwdw);
CArchive& operator<<(LONGLONG dwdw);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка, `CArchive` которая позволяет нескольким операторам вставки на одной строке.

### <a name="remarks"></a>Remarks

Последние две версии выше, специально для хранения 64-битных рядов.

Если вы использовали IMPLEMENT_SERIAL макрос в реализации класса, то `CObject` оператор вставки перегружен для вызовов защищенного. `WriteObject` Эта функция, в свою `Serialize` очередь, вызывает функцию класса.

Оператор вставки [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) (<<) поддерживает диагностический демпинг и хранение в архиве.

### <a name="example"></a>Пример

Этот пример демонстрирует использование `CArchive` оператора вставки << с **int** и **длинными** типами.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Пример

Этот пример 2 демонстрирует использование `CArchive` оператора вставки `CStringT` << с типом.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

## <a name="carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a>CArchive::оператор&gt;&gt;

Загружает указанный объект или примитивный тип из архива.

```
friend CArchive& operator>>(
    CArchive& ar,
    CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

friend CArchive& operator>>(
    CArchive& ar,
    const CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator>>(BYTE& by);
CArchive& operator>>(WORD& w);
CArchive& operator>>(int& i);
CArchive& operator>>(LONG& l);
CArchive& operator>>(DWORD& dw);
CArchive& operator>>(float& f);
CArchive& operator>>(double& d);
CArchive& operator>>(short& w);
CArchive& operator>>(char& ch);
CArchive& operator>>(wchar_t& ch);
CArchive& operator>>(unsigned& u);
CArchive& operator>>(bool& b);
CArchive& operator>>(ULONGLONG& dwdw);
CArchive& operator>>(LONGLONG& dwdw);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка, `CArchive` которая позволяет нескольким операторам извлечения на одной линии.

### <a name="remarks"></a>Remarks

Последние две версии выше, специально для загрузки 64-битных рядов.

Если вы использовали IMPLEMENT_SERIAL макрос в реализации класса, `CObject` то операторы извлечения перегружены для вызова защищенной `ReadObject` функции (с ненулевой указателем времени выполнения). Эта функция, в свою `Serialize` очередь, вызывает функцию класса.

Оператор извлечения [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) (>>) поддерживает загрузку из архива.

### <a name="example"></a>Пример

Этот пример демонстрирует использование `CArchive` оператора экстракции >> с типом **int.**

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Пример

Этот пример демонстрирует использование `CArchive` операторов вставки \< и извлечения <и >> с типом. `CStringT`

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

## <a name="carchiveread"></a><a name="read"></a>CArchive::Читать

Читает указанное количество байтов из архива.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на буфер, поставляемый пользователем, который должен получать данные, считываемые из архива.

*nMax*<br/>
Неподписанный целый ряд с указанием количества байтов, которые будут прочитаны из архива.

### <a name="return-value"></a>Возвращаемое значение

Неподписанный целый ряд, содержащий количество байтов на самом деле читать. Если значение возврата меньше запрошенного числа, конец файла достигнут. На состояние конца файла не выбрасывается никаких исключений.

### <a name="remarks"></a>Remarks

Архив не интерпретирует байты.

Вы можете `Read` использовать функцию `Serialize` члена в вашей функции для чтения обычных структур, которые содержатся в ваших объектах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

## <a name="carchivereadclass"></a><a name="readclass"></a>CArchive::ReadClass

Вызовите эту функцию участника, чтобы прочитать ссылку на класс, ранее хранимый с [WriteClass.](#writeclass)

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>Параметры

*pClassRefRequested*<br/>
Указатель на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) которая соответствует запрошенной ссылке класса. Может иметь значение NULL.

*pSchema*<br/>
Указатель на схему класса времени выполнения, ранее хранящийся.

*pObTag*<br/>
Номер, относягайский к уникальному тегу объекта. Используется внутренне при реализации [ReadObject](#readobject). Подвергается только для продвинутого программирования; *pObTag* обычно должен быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [CRuntimeClass.](../../mfc/reference/cruntimeclass-structure.md)

### <a name="remarks"></a>Remarks

Если *pClassRefRequested* не `ReadClass` является NULL, проверяется, что архивная информация класса совместима с классом времени выполнения. Если это не совместимо, `ReadClass` будет бросать [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Класс времени выполнения должен использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL;](../../mfc/reference/run-time-object-model-services.md#implement_serial) в `ReadClass` противном случае, будет бросать [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Если *pSchema* является NULL, схема сохраненного класса может быть извлечена, позвонив в [CArchive::GetObjectSchema](#getobjectschema); в <strong>\*</strong>противном случае *pSchema* будет содержать схему класса времени выполнения, которая ранее хранилась.

Вы можете использовать [SerializeClass](#serializeclass) вместо `ReadClass`, который обрабатывает как чтение и написание ссылки класса.

### <a name="example"></a>Пример

  Смотрите пример [CArchive::WriteClass](#writeclass).

## <a name="carchivereadobject"></a><a name="readobject"></a>CArchive::ReadObject

Читает данные объектов из архива и строит объект соответствующего типа.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>Параметры

*pClass*<br/>
Постоянная указка на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) соответствующую объекту, который вы ожидаете прочитать.

### <a name="return-value"></a>Возвращаемое значение

Указатель [CObject,](../../mfc/reference/cobject-class.md) который должен быть безопасно отлит в правильный производный класс с помощью [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается `CArchive` экстракции () **>>** оператор перегружен для [указателя CObject.](../../mfc/reference/cobject-class.md) `ReadObject`, в свою `Serialize` очередь, вызывает функцию архивного класса.

Если вы поставляете параметр ненулевого *pClass,* который получен [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макросом, то функция проверяет класс времени выполнения архивируемого объекта. Это предполагает, что вы использовали IMPLEMENT_SERIAL макрос в реализации класса.

### <a name="example"></a>Пример

  Смотрите пример [CArchive::WriteObject](#writeobject).

## <a name="carchivereadstring"></a><a name="readstring"></a>CArchive::ReadString

Вызовите эту функцию участника для чтения текстовых `CArchive` данных в буфер из файла, связанного с объектом.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылка на [CString,](../../atl-mfc-shared/reference/cstringt-class.md) которая будет содержать резуцивую строку после считывания из файла, связанного с объектом CArchive.

*lpsz*<br/>
Укажите указатель на буфер, поставляемый пользователем, который получит строку текста с нулевым завершением.

*nMax*<br/>
Определяет максимальное количество символов для чтения. Должно быть на один меньше, чем размер буфера *lpsz.*

### <a name="return-value"></a>Возвращаемое значение

В версии, которая возвращает BOOL, ПРАВДА, если успешно; FALSE в противном случае.

В версии, `LPTSTR`которая возвращает указатель на буфер, содержащий текстовые данные; NULL, если конец файла был достигнут.

### <a name="remarks"></a>Remarks

В версии функции участника с параметром *nMax* буфер будет вмещать до предела *nMax* - 1 символ. Чтение останавливается парой кормов для возврата вагона. Трейлинг новых символов всегда удаляются. В любом случае приложен нулевой символ (''0'.

[CArchive::Read](#read) также доступен для ввода текстового режима, но он не прекращается на паре кормов для возврата каретки.

### <a name="example"></a>Пример

  Смотрите пример для [CArchive::WriteString](#writestring).

## <a name="carchiveserializeclass"></a><a name="serializeclass"></a>CArchive::SerializeClass

Вызовите эту функцию участника, когда вы хотите хранить и загружать информацию о версии базового класса.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Параметры

*pClassRef*<br/>
Указатель на объект класса времени выполнения для базового класса.

### <a name="remarks"></a>Remarks

`SerializeClass`читает или пишет ссылку на `CArchive` класс к объекту, `CArchive`в зависимости от направления . Используйте `SerializeClass` вместо [ReadClass](#readclass) и [WriteClass](#writeclass) как удобный способ сериализации объектов базового класса; `SerializeClass` требует меньше кода и меньше параметров.

Например, `ReadClass` `SerializeClass` проверяется, что архивная информация класса совместима с классом времени выполнения. Если это не совместимо, `SerializeClass` будет бросать [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Класс времени выполнения должен использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL;](../../mfc/reference/run-time-object-model-services.md#implement_serial) в `SerializeClass` противном случае, будет бросать [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Используйте [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос для получения значения для параметра *pRuntimeClass.* Базовый класс должен использовать [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

## <a name="carchivesetloadparams"></a><a name="setloadparams"></a>CArchive::SetLoadParams

Звоните, `SetLoadParams` когда вы собираетесь `CObject`прочитать большое количество полученных объектов из архива.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Параметры

*nGrowBy*<br/>
Минимальное количество слотов элементов, чтобы выделить, если увеличение размера необходимо.

### <a name="remarks"></a>Remarks

`CArchive`использует массив нагрузки для устранения ссылок на объекты, хранящиеся в архиве. `SetLoadParams`позволяет установить размер, к которому растет массив нагрузки.

Вы не `SetLoadParams` должны звонить после загрузки объекта или после вызова [MapObject](#mapobject) или [ReadObject.](#readobject)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivesetobjectschema"></a><a name="setobjectschema"></a>CArchive::SetObjectSchema

Вызовите эту функцию участника, чтобы установить схему объекта, хранящуюся в объекте архива, на *nSchema.*

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Параметры

*nЧема*<br/>
Определяет схему объекта.

### <a name="remarks"></a>Remarks

Следующий вызов [GetObjectSchema](#getobjectschema) вернет значение, хранящееся в *nSchema.*

Использование `SetObjectSchema` для продвинутых версий; например, если требуется заставить определенную версию читаться в `Serialize` функции производной версии.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

## <a name="carchivesetstoreparams"></a><a name="setstoreparams"></a>CArchive::SetStoreParams

Используйте `SetStoreParams` при хранении большого количества полученных `CObject`объектов в архиве.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Параметры

*nHashSize*<br/>
Размер таблицы хэша для карт указателей интерфейса. Должно быть простое число.

*nBlockSize*<br/>
Определяет детализацию распределения памяти для расширения параметров. Должна быть сила 2 для лучшей производительности.

### <a name="remarks"></a>Remarks

`SetStoreParams`позволяет установить размер таблицы хэша и размер блока карты, используемой для идентификации уникальных объектов в процессе сериализации.

Вы не `SetStoreParams` должны звонить после хранения каких-либо объектов или после вызова [MapObject](#mapobject) или [WriteObject.](#writeobject)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivewrite"></a><a name="write"></a>CArchive::Запись

Записывает указанное количество байтов в архив.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Параметры

*lpBuf*<br/>
Указатель на буфер, поставляемый пользователем, содержащий данные, которые должны быть записаться в архив.

*nMax*<br/>
Целый ряд, который определяет количество байтов, которые будут записаны в архив.

### <a name="remarks"></a>Remarks

Архив не форматирует байты.

Вы можете `Write` использовать функцию `Serialize` члена в вашей функции для записи обычных структур, которые содержатся в ваших объектах.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

## <a name="carchivewriteclass"></a><a name="writeclass"></a>CArchive::WriteClass

Используйте `WriteClass` для хранения версии и классовой информации базового класса во время сериализации производного класса.

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Параметры

*pClassRef*<br/>
Указатель на структуру [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) которая соответствует запрошенной ссылке класса.

### <a name="remarks"></a>Remarks

`WriteClass`пишет ссылку на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для базового класса на `CArchive`. Используйте [CArchive::ReadClass](#readclass) для получения ссылки.

`WriteClass`проверяет, что архивная информация класса совместима с классом времени выполнения. Если это не совместимо, `WriteClass` будет бросать [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Класс времени выполнения должен использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL;](../../mfc/reference/run-time-object-model-services.md#implement_serial) в `WriteClass` противном случае, будет бросать [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Вы можете использовать [SerializeClass](#serializeclass) вместо `WriteClass`, который обрабатывает как чтение и написание ссылки класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

## <a name="carchivewriteobject"></a><a name="writeobject"></a>CArchive::WriteObject

Хранит указанное `CObject` в архиве.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Параметры

*Тн*<br/>
Постоянная указка на сохраненный объект.

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается `CArchive` вставкой **<<**() оператор `CObject`перегружен для . `WriteObject`, в свою `Serialize` очередь, вызывает функцию архивного класса.

Для включения архивирования необходимо использовать IMPLEMENT_SERIAL макрос. `WriteObject`записывает название класса ASCII в архив. Это имя класса проверяется позже во время процесса загрузки. Специальная схема кодирования предотвращает ненужное дублирование названия класса для нескольких объектов класса. Эта схема также предотвращает избыточное хранение объектов, которые являются мишенями более чем одного указателя.

Точный метод кодирования объектов (включая наличие имени класса ASCII) является деталью реализации и может измениться в будущих версиях библиотеки.

> [!NOTE]
> Закройте создание, удалите и обновим все объекты, прежде чем начать их архивировать. Ваш архив будет поврежден, если вы смешиваете архивирование с модификацией объекта.

### <a name="example"></a>Пример

Для определения класса `CAge`см. пример [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

## <a name="carchivewritestring"></a><a name="writestring"></a>CArchive::WriteString

Используйте эту функцию члена для записи данных из буфера в файл, связанный с объектом. `CArchive`

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Обращена указатель на буфер, содержащий нулевую строку текста.

### <a name="remarks"></a>Remarks

Прекращение нулевого символа (''0') не записано в файл; и новая строка не написана автоматически.

`WriteString`бросает исключение в ответ на несколько условий, в том числе диск-полное состояние.

`Write`также доступен, но вместо того, чтобы прекращать на нулевой символ, он пишет запрошенное количество байтов в файл.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Класс CSocket](../../mfc/reference/csocket-class.md)<br/>
[Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
