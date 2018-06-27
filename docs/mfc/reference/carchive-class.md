---
title: CArchive-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0bfca3c6e42c8b4efa6cd29d86a30f36fc394f5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952509"
---
# <a name="carchive-class"></a>CArchive-класс
Позволяет сохранить сложную сеть объектов в перманентной двоичной форме (обычно на запоминающем устройстве), сохраняющейся даже после удаления объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CArchive  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|Создает объект `CArchive`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|Закрывает архив без вызова исключения.|  
|[CArchive::Close](#close)|Очищает незаписанных данных и отключается от `CFile`.|  
|[CArchive::Flush](#flush)|Очищает незаписанных данных из буфера архива.|  
|[CArchive::GetFile](#getfile)|Возвращает `CFile` указатель на объект для этого архива.|  
|[CArchive::GetObjectSchema](#getobjectschema)|Вызывается из `Serialize` функцию, чтобы определить версию объекта, который десериализуется.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Определяет ли буфер был очищен во время Windows Sockets процесс получения.|  
|[CArchive::IsLoading](#isloading)|Определяет, загружается ли архива.|  
|[CArchive::IsStoring](#isstoring)|Определяет, ли хранения архива.|  
|[CArchive::MapObject](#mapobject)|Объекты помещаются в схеме, которые не сериализуются в файл, но, доступных для вложенных объектов для ссылки.|  
|[CArchive::Read](#read)|Считывает необработанные байты.|  
|[CArchive::ReadClass](#readclass)|Операции чтения с ранее хранятся ссылки на класс `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Вызывает объект `Serialize` функции для загрузки.|  
|[CArchive::ReadString](#readstring)|Считывает одну строку текста.|  
|[CArchive::SerializeClass](#serializeclass)|Считывает или записывает ссылку на класс `CArchive` объект в зависимости от направления `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|Задает размер, к которому увеличения нагрузки массива. Должен вызываться перед загрузкой любого объекта, или перед `MapObject` или `ReadObject` вызывается.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Задает схему объекта, хранящиеся в объекте архива.|  
|[CArchive::SetStoreParams](#setstoreparams)|Задает размер хэш-таблицы и размер блока карты, используемый для идентификации уникальные объекты во время сериализации.|  
|[CArchive::Write](#write)|Записывает необработанные байты.|  
|[CArchive::WriteClass](#writeclass)|Записывает ссылку на `CRuntimeClass` для `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Вызывает объект `Serialize` функции для хранения.|  
|[CArchive::WriteString](#writestring)|Записывает одну строку текста.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|Хранит объекты и типы-примитивы в архив.|  
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|Загружает объекты и типы-примитивы из архива.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Примечания  
 `CArchive` не имеет базового класса.  
  
 Позже объекты можно загрузить из постоянного хранилища реконструкцию их в памяти. Этот процесс внесения постоянных данных называется «сериализация».  
  
 Можно рассматривать объект архива в качестве своего рода двоичного потока. Как и поток ввода вывода архив связан с файлом и позволяет использовать буфер записи и чтения данных из хранилища и. Поток ввода вывода обрабатывает последовательности символов ASCII, но двоичный объект данных в формате эффективных и неизбыточной обрабатывает архив.  
  
 Необходимо создать [CFile](../../mfc/reference/cfile-class.md) объекта перед созданием `CArchive` объекта. Кроме того необходимо убедиться, что состояние загрузки или сохранения архива совместим с режима открытия файла. Не более одного активного архив каждого файла.  
  
 При построении `CArchive` объекта, присоединить ее к объекту класса `CFile` (или производный класс), представляющий открытый файл. Вы также указать, будет ли использован для загрузки или сохранения архива. Объект `CArchive` объекта может обрабатывать не только типы-примитивы, но объекты [CObject](../../mfc/reference/cobject-class.md)-производные классы, предназначенные для сериализации. Сериализуемый класс обычно имеет `Serialize` функция-член, который обычно использует [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макросов, как описано в разделе класса `CObject`.  
  
 Перегруженные извлечения ( **>>**) и вставки ( **<<**) операторы — это удобный архив программные интерфейсы, которые поддерживают обоих типов-примитивов и `CObject` -производные классы.  
  
 `CArchive` также поддерживает программирование с использованием классов MFC Windows Sockets [CSocket](../../mfc/reference/csocket-class.md) и [CSocketFile](../../mfc/reference/csocketfile-class.md). [IsBufferEmpty](#isbufferempty) функция-член поддерживает такого использования.  
  
 Дополнительные сведения о `CArchive`, см. в статьях [сериализации](../../mfc/serialization-in-mfc.md) и [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CArchive`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="abort"></a>  CArchive::Abort  
 Вызывайте эту функцию, чтобы закрыть архив без вызова исключения.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Примечания  
 `CArchive` Обычно вызывает деструктор `Close`, который будут удалены все данные, не были сохранены в связанный обработчик `CFile` объекта. Это может привести к исключениям.  
  
 Если перехватывать эти исключения, рекомендуется использовать `Abort`, после чего destructing `CArchive` объекта не привести к возникновению других исключений. При обработке исключений, `CArchive::Abort` не будет вызывать исключение при сбое, потому что, в отличие от [CArchive::Close](#close), `Abort` игнорирует ошибки.  
  
 Если вы использовали **новый** для выделения `CArchive` объекта в куче, необходимо удалить его после закрытия файла.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArchive::WriteClass](#writeclass).  
  
##  <a name="carchive"></a>  CArchive::CArchive  
 Создает `CArchive` и указывает, является ли он будет использоваться для загрузки или хранения объектов.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pFile*  
 Указатель на `CFile` объект, являющийся первичным источником или назначением постоянных данных.  
  
 *nMode*  
 Флаг, указывающий, будут ли объекты загружаются из или сохранена в архиве. *NMode* параметр должен иметь одно из следующих значений:  
  
- **CArchive::load** загружает данные из архива. Требуется только `CFile` разрешение на чтение.  
  
- **CArchive::store** сохраняет данные в архив. Требуется `CFile` разрешение на запись.  
  
- **CArchive::bNoFlushOnDelete** предотвращает автоматический вызов архив `Flush` при вызове деструктора архива. Если этот флажок установлен, вы несете ответственность за явного вызова `Close` перед вызовом деструктора. Если этого не сделать, данные будут повреждены.  
  
 *nBufSize*  
 Целое число, определяющее размер буфера внутреннего файла в байтах. Обратите внимание, что размер буфера по умолчанию равен 4 096 байт. Если вы регулярно архивируете больших объектов, можно улучшить производительность при использовании больший размер буфера, кратной размеру буфера файла.  
  
 *lpBuf*  
 Необязательный указатель на буфер, предоставленный пользователем размера *nBufSize*. Если этот параметр не задан, архив выделяет буфер в локальной куче и освобождает его, если объект уничтожен. Архив не позволяет освободить буфер, предоставленный пользователем.  
  
### <a name="remarks"></a>Примечания  
 Эта спецификация нельзя изменить после создания архива.  
  
 Вы не имеете права использовать `CFile` операций для изменения состояния файла до закрытия архива. Любой такой операции приведет к повреждению целостности архива. Доступ к положение указателя файла в любой момент во время сериализации, получая объект файл архива из [GetFile](#getfile) функции-члена, а затем с помощью [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) функции . Необходимо вызвать [CArchive::Flush](#flush) перед получением положение указателя файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>  CArchive::Close  
 Очищает все данные, оставшиеся в буфере, закрывает архива и отключает из файла архива.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Дальнейшие операции архива не разрешены. После того как вы закроете архив, можно создать другой архив в том же файле, или можно закрыть файл.  
  
 Функция-член `Close` гарантирует, что все данные, передаваемые в файл из архива и делает архив недоступной. Для завершения передачи файла для среды хранения, необходимо сначала использовать [CFile::Close](../../mfc/reference/cfile-class.md#close) и затем удалите `CFile` объекта.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArchive::WriteString](#writestring).  
  
##  <a name="flush"></a>  CArchive::Flush  
 Вызывает запись данных, остающихся в буфере для записи в файл архива.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член `Flush` гарантирует, что все данные передаются из архива в файл. Необходимо вызвать [CFile::Close](../../mfc/reference/cfile-class.md#close) для завершения передачи файла для среды хранения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>  CArchive::GetFile  
 Возвращает `CFile` указатель на объект для этого архива.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный указатель `CFile` объект используется.  
  
### <a name="remarks"></a>Примечания  
 Необходимо записать архив перед использованием `GetFile`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema  
 Вызывайте эту функцию из `Serialize` функции, чтобы определить версию объекта, который был десериализован.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Во время десериализации, версию объекта выполняется чтение.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции действителен только при `CArchive` загружен объект ( [CArchive::IsLoading](#isloading) возвращает ненулевое значение). Он должен быть первый вызов в `Serialize` функции и вызван только один раз. Возвращаемое значение ( **UINT**) -1 означает, что номер версии неизвестно.  
  
 Объект `CObject`-производный класс может использовать **VERSIONABLE_SCHEMA** вместе (с помощью побитового **или**) с версией схемы сам (в IMPLEMENT_SERIAL-макрос) для создания «поддержкой объект», то есть которого `Serialize` функция-член можно прочитать несколько версий. Функциональные возможности framework по умолчанию (без **VERSIONABLE_SCHEMA**) — создать исключение при несовпадении версии.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty  
 Вызовите эту функцию-член для определения того, пуста ли архивный объект внутреннего буфера.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив буфер пуст; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляется для поддержки программирования MFC Windows Sockets в классе `CSocketFile`. Необходимо использовать его для архива, связанные с `CFile` объекта.  
  
 Причины для использования `IsBufferEmpty` архивом, связанные с `CSocketFile` объект является то, что архив буфер может содержать более одного сообщения или записи. После получения одно сообщение, следует использовать `IsBufferEmpty` для управления циклом, по-прежнему получение данных, пока буфер пуст. Дополнительные сведения см. в разделе [Receive](../../mfc/reference/casyncsocket-class.md#receive) функции-члена класса `CAsyncSocket`, который показывает, как использовать `IsBufferEmpty`.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isloading"></a>  CArchive::IsLoading  
 Определяет, загружается ли архив данных.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив в настоящее время используется для загрузки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивированные классов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>  CArchive::IsStoring  
 Определяет, является ли архив хранения данных.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив в настоящее время используется для хранения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивированные классов.  
  
 Если `IsStoring` архив состояние отлично от нуля, то его `IsLoading` состояние имеет значение 0 и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>  CArchive::MapObject  
 Вызовите эту функцию-член для размещения объектов на карте, фактически не сериализуются в файл, но, доступных для вложенных объектов для ссылки.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Параметры  
 *почтовый ящик*  
 Постоянный указатель для хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Например не может сериализовать документ, но будет сериализовать элементы, которые являются частью документа. Путем вызова `MapObject`, разрешить элементов и подчиненных, ссылка на документ. Кроме того, можно сериализовать сериализованный подэлементы их *m_pDocument* обратный указатель.  
  
 Можно вызвать `MapObject` при сохранения и загрузки из `CArchive` объекта. `MapObject` Добавляет указанный объект в структурах внутренних данных, поддерживаемых `CArchive` объекта во время сериализации и десериализации, но в отличие от [ReadObject](#readobject) и [WriteObject](#writeobject) **,** не вызывает сериализации объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>  CArchive::m_pDocument  
 Значение **NULL** по умолчанию этот указатель `CDocument` может быть задано пользователь `CArchive` экземпляра требуется.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Примечания  
 Распространенным вариантом применения этого указателя — для передачи дополнительных сведений об процесс сериализации для сериализации все объекты. Это достигается путем инициализации указатель с документом ( `CDocument`-производного класса), сериализуемый, таким образом, что объекты в документе можно доступа к документу, при необходимости. Этот указатель используется также `COleClientItem` объекты во время сериализации.  
  
 Задает framework *m_pDocument* в документ, сериализуемый в случае, когда пользователь выполняет файл открыть или сохранить команды. При сериализации объекта связывания и внедрения (OLE) документе-контейнере для причинам, отличным от открытия файла или сохранение, необходимо явно задать *m_pDocument*. Например вам может потребоваться при сериализации документа-контейнера в буфер обмена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;  
 Сохраняет указанный объект или тип-примитив в архив.  
  
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
 Объект `CArchive` ссылку, которая включает несколько операторов вставки в одной строке.  
  
### <a name="remarks"></a>Примечания  
 Двух последних версиях выше, в частности, для хранения 64-разрядных целых чисел.  
  
 Если вы использовали IMPLEMENT_SERIAL-макрос в реализации класса, то перегруженный оператор вставки для `CObject` вызывает защищенный `WriteObject`. Эта функция, в свою очередь, вызывает `Serialize` функции класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) оператор вставки (<<) поддерживает диагностики формирование дампа и хранение в архив.  
  
### <a name="example"></a>Пример  
 В этом примере показано использование функции `CArchive` оператора вставки << с **int** и **длинные** типов.  
  
 [!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере 2 показано использование функции `CArchive` оператора вставки << с `CStringT` типа.  
  
 [!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;  
 Загружает указанный объект или тип-примитив из архива.  
  
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
 Объект `CArchive` ссылку, которая включает несколько операторов извлечения в одной строке.  
  
### <a name="remarks"></a>Примечания  
 Двух последних версиях выше, в частности, для загрузки 64-разрядных целых чисел.  
  
 Если вы использовали IMPLEMENT_SERIAL-макрос в реализации класса, то перегруженные операторы извлечения для `CObject` вызовите защищенный `ReadObject` функция (указатель ненулевое значение, класс среды выполнения). Эта функция, в свою очередь, вызывает `Serialize` функции класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) оператор извлечения (>>) поддерживает загрузку из архива.  
  
### <a name="example"></a>Пример  
 В этом примере показано использование функции `CArchive` оператор извлечения >> с **int** типа.  
  
 [!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере показано использование функции `CArchive` операторов вставки и извлечения <\< и >> с `CStringT` типа.  
  
 [!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>  CArchive::Read  
 Считывает указанное число байтов из архива.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *lpBuf*  
 Указатель на буфер, предоставленный пользователем, получающего данные, считанные из архива.  
  
 *nMax*  
 Целое число без знака указав число байтов для считывания из архива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число без знака, содержащее число фактически считанных байтов. Если возвращаемое значение меньше запрошенного числа, был достигнут конец файла. Исключение не возникает при условии конечного файла.  
  
### <a name="remarks"></a>Примечания  
 Архив не интерпретирует байты.  
  
 Можно использовать `Read` функции-члена внутри вашей `Serialize` функцию для считывания обычные структуры, которые содержатся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>  CArchive::ReadClass  
 Вызовите эту функцию-член для чтения ссылка на класс, сохраненные ранее с [WriteClass](#writeclass).  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRefRequested*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует запросу ссылки на класс. Может быть **NULL**.  
  
 *pSchema*  
 Указатель на схемы, сохраненные ранее класса во время выполнения.  
  
 *pObTag*  
 Число, которое ссылается на уникальный тег объекта. Используется системой реализации [ReadObject](#readobject). Предоставляются дополнительные программирования *pObTag* обычно должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Если *pClassRefRequested* не **NULL**, `ReadClass` проверяет, является ли информация о классе архивированные совместим с вашего класса среды выполнения. Если он не совместим, `ReadClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае `ReadClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Если *pSchema* — **NULL**, можно извлечь схему хранимой класса путем вызова [CArchive::GetObjectSchema](#getobjectschema); в противном случае **\**** pSchema* будет содержать схему класса среды выполнения, которая ранее была сохранена.  
  
 Можно использовать [SerializeClass](#serializeclass) вместо `ReadClass`, которая обрабатывает чтение и запись ссылки на класс.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArchive::WriteClass](#writeclass).  
  
##  <a name="readobject"></a>  CArchive::ReadObject  
 Считывает данные объекта из архива и создает объект соответствующего типа.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Параметры  
 *pClass*  
 Постоянный указатель [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры, соответствующей объекту, предполагается, что для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CObject](../../mfc/reference/cobject-class.md) указатель, который необходимо безопасно привести к нужному серверу производного класса с помощью [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается методом `CArchive` извлечения ( **>>**) перегруженный оператор для [CObject](../../mfc/reference/cobject-class.md) указателя. `ReadObject`, в свою очередь, вызывает `Serialize` функция архивированные класса.  
  
 При указании ненулевое *pClass* параметр, который можно получить путем [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макроса, то функция проверяет класс архивированные объекта во время выполнения. Это предполагается, что вы использовали IMPLEMENT_SERIAL-макрос в реализацию класса.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArchive::WriteObject](#writeobject).  
  
##  <a name="readstring"></a>  CArchive::ReadString  
 Вызовите эту функцию-член для чтения текстовых данных в буфер из файла, связанного с `CArchive` объекта.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) после чтения из файла, связанного с объектом CArchive, содержащий результирующие строки.  
  
 *lpsz*  
 Задает указатель на пользовательские буфера, который будет принимать строку текста с завершающим нулем.  
  
 *nMax*  
 Указывает максимальное число считываемых символов. Должна быть одна меньше, чем размер *lpsz* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В версии, который возвращает **BOOL**, **TRUE** в случае успешного выполнения; **FALSE** в противном случае.  
  
 В версии, который возвращает `LPTSTR`, указатель на буфер, содержащий текстовые данные; **NULL** если достигнут конец файла.  
  
### <a name="remarks"></a>Примечания  
 В версии этой функции *nMax* параметра, будет содержаться в буфере ограничению *nMax* - 1 символов. Чтение остановлена с помощью пары перевода строки возврата каретки. Всегда удаляются конечные символы новой строки. В любом случае добавляется символ null («\0»).  
  
 [CArchive::Read](#read) также доступна для входных данных в текстовом режиме, но не прекращает на пару перевода строки возврата каретки.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CArchive::WriteString](#writestring).  
  
##  <a name="serializeclass"></a>  CArchive::SerializeClass  
 Вызовите эту функцию-член, при необходимости для сохранения и загрузки сведений о версии базового класса.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRef*  
 Указатель на объект класса среды выполнения для базового класса.  
  
### <a name="remarks"></a>Примечания  
 `SerializeClass` Считывает или записывает ссылку на класс `CArchive` объект, в зависимости от направления `CArchive`. Используйте `SerializeClass` вместо [ReadClass](#readclass) и [WriteClass](#writeclass) — удобный способ сериализации объектов базового класса; `SerializeClass` требует меньшего объема кода и меньшее количество параметров.  
  
 Как `ReadClass`, `SerializeClass` проверяет, является ли информация о классе архивированные совместим с вашего класса среды выполнения. Если он не совместим, `SerializeClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае `SerializeClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Используйте [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос для извлечения значения для *pRuntimeClass* параметра. Базовый класс должен использован [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>  CArchive::SetLoadParams  
 Вызовите `SetLoadParams` когда вы планируете считывать большое количество `CObject`-объектов, производных из архива.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Параметры  
 *nGrowBy*  
 Минимальное число слотов элемент для выделения, если увеличение размера не требуется.  
  
### <a name="remarks"></a>Примечания  
 `CArchive` Массив нагрузки используется для разрешения ссылок на объекты, хранящиеся в архиве. `SetLoadParams` позволяет задать размер, к которому увеличения нагрузки массива.  
  
 Не следует вызывать `SetLoadParams` после загрузки любого объекта, или после [MapObject](#mapobject) или [ReadObject](#readobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema  
 Вызовите эту функцию-член для задания объектов схемы, хранящиеся в объекте архива для *nSchema*.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Параметры  
 *nSchema*  
 Указывает схемы объекта.  
  
### <a name="remarks"></a>Примечания  
 При следующем вызове [GetObjectSchema](#getobjectschema) возвращает значение, хранящееся в *nSchema*.  
  
 Используйте `SetObjectSchema` для расширенного управления версиями; например, если вы хотите принудительно применить определенную версию для чтения в `Serialize` функция производного класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>  CArchive::SetStoreParams  
 Используйте `SetStoreParams` при хранении большое количество `CObject`-производных объектов в архив.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Параметры  
 *nHashSize*  
 Сопоставляет размер хэш-таблицы для указателя интерфейса. Должно быть простое число.  
  
 *nBlockSize*  
 Указывает гранулярность выделения памяти для расширения параметров. Должно быть степенью числа 2 для повышения производительности.  
  
### <a name="remarks"></a>Примечания  
 `SetStoreParams` позволяет задать размер хэш-таблицы и размер блока карты, используемый для идентификации уникальные объекты во время сериализации.  
  
 Не следует вызывать `SetStoreParams` после хранятся все объекты, или [MapObject](#mapobject) или [WriteObject](#writeobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>  CArchive::Write  
 Записывает указанное число байтов в архив.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *lpBuf*  
 Указатель на буфер, предоставленный пользователем, содержащий данные, которые требуется записать в архив.  
  
 *nMax*  
 Целое число, указывающее число байтов для записи в архив.  
  
### <a name="remarks"></a>Примечания  
 Архив не форматирует байты.  
  
 Можно использовать `Write` функции-члена внутри вашей `Serialize` функции для записи обычных структуры, содержащихся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>  CArchive::WriteClass  
 Используйте `WriteClass` обеспечить хранение версии и класс базового класса во время сериализации производного класса.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRef*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует запросу ссылки на класс.  
  
### <a name="remarks"></a>Примечания  
 `WriteClass` Записывает ссылку на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для базового класса, чтобы `CArchive`. Используйте [CArchive::ReadClass](#readclass) для получения ссылок.  
  
 `WriteClass` проверяет, что информация о классе архивированные совместимость с класса среды выполнения. Если он не совместим, `WriteClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае `WriteClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Можно использовать [SerializeClass](#serializeclass) вместо `WriteClass`, которая обрабатывает чтение и запись ссылки на класс.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>  CArchive::WriteObject  
 Сохраняет указанный `CObject` в архив.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Параметры  
 *почтовый ящик*  
 Постоянный указатель для хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается методом `CArchive` вставки ( **<<**) перегруженный оператор для `CObject`. `WriteObject`, в свою очередь, вызывает `Serialize` функция архивированные класса.  
  
 Необходимо использовать `IMPLEMENT_SERIAL` макрос, чтобы включить архивирование. `WriteObject` Записывает имя класса ASCII в архив. Это имя класса проверяется позднее, во время процесса загрузки. Специальные кодировки не допускает дублирования имя класса для нескольких объектов класса. Эта схема также предотвращает избыточное хранилище объекты, являющиеся целевыми для более чем один указатель.  
  
 Точный объект кодировку (включая наличие имени класса ASCII) метод в реализации и может измениться в будущих версиях библиотеки.  
  
> [!NOTE]
>  Завершите создание, удаление и обновление всех объектов, прежде чем приступать к архивировать их. Если смешать архивация с изменения объекта архива будут повреждены.  
  
### <a name="example"></a>Пример  
 Для определения класса `CAge`, см. пример для [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>  CArchive::WriteString  
 Используйте эту функцию-член для записи данных из буфера в файл, связанный с `CArchive` объекта.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 *lpsz*  
 Задает указатель на буфер, содержащий строку текста с завершающим нулем.  
  
### <a name="remarks"></a>Примечания  
 Завершающий символ null (\0) не записывается в файл. а также новая строка автоматически записывается.  
  
 `WriteString` Возникло исключение в ответ на несколько условий, включая условия переполнения диска.  
  
 `Write` также доступна, но вместо заканчивается на символ null, он записывает запрошенное число байт в файл.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [CSocket-класс](../../mfc/reference/csocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
