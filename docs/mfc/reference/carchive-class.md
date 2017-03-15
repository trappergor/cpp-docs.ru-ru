---
title: "CArchive-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], archiving objects
- CArchive class
- serialization [C++], CArchive class
- storage [C++], CArchive class
- data storage [C++], CArchive class
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 501b365678a45148aabe638ff341f3ae995e4ab5
ms.lasthandoff: 02/24/2017

---
# <a name="carchive-class"></a>CArchive-класс
Позволяет сохранить сложную сеть объектов в перманентной двоичной форме (обычно на запоминающем устройстве), сохраняющейся даже после удаления объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CArchive  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|Создает объект `CArchive`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|Закрывает архив без создания исключения.|  
|[CArchive::Close](#close)|Очищает незаписанных данных и отключается от `CFile`.|  
|[CArchive::Flush](#flush)|Очищает незаписанных данных из буфера архива.|  
|[CArchive::GetFile](#getfile)|Возвращает `CFile` указатель на объект для этого архива.|  
|[CArchive::GetObjectSchema](#getobjectschema)|Вызывается из `Serialize` функции, чтобы определить версию объекта, который был десериализован.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Определяет ли буфер был очищен во время Windows Sockets процесс получения.|  
|[CArchive::IsLoading](#isloading)|Определяет, загружается ли архив.|  
|[CArchive::IsStoring](#isstoring)|Определяет, ли хранения архива.|  
|[CArchive::MapObject](#mapobject)|Размещает объекты в схеме, не сериализуются в файл, но, доступных для подчиненных для ссылки.|  
|[CArchive::Read](#read)|Считывает необработанные байты.|  
|[CArchive::ReadClass](#readclass)|Чтений с ранее сохраненным ссылку на класс `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Вызывает объект `Serialize` функции для загрузки.|  
|[CArchive::ReadString](#readstring)|Считывает одну строку текста.|  
|[CArchive::SerializeClass](#serializeclass)|Считывает или записывает ссылку на класс `CArchive` объекта в зависимости от направления `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|Задает размер, к которому роста нагрузки массива. Должен вызываться перед загрузкой любой объект, или перед `MapObject` или `ReadObject` вызывается.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Задает схему объекта, хранящихся в объекте архива.|  
|[CArchive::SetStoreParams](#setstoreparams)|Задает размер хэш-таблицы и размер блока карты, используемый для определения уникальных объектов в процессе сериализации.|  
|[CArchive::Write](#write)|Записывает необработанные байты.|  
|[CArchive::WriteClass](#writeclass)|Записывает ссылку на `CRuntimeClass` в `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Вызывает объект `Serialize` функции для хранения.|  
|[CArchive::WriteString](#writestring)|Записывает одну строку текста.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArchive::operator&lt;&lt;](#operator_lt_lt)|Хранит объекты и типы-примитивы в архив.|  
|[CArchive::operator&gt;&gt;](#operator_gt_gt)|Загружает объекты и типы-примитивы из архива.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Примечания  
 `CArchive`не имеет базового класса.  
  
 Позже можно загрузить объекты из постоянного хранилища, восстановление их в памяти. Этот процесс внесения постоянных данных называется «сериализация».  
  
 Можно представить объект архива как своего рода двоичного потока. Как и поток ввода вывода архив связан с файлом и разрешает буфере запись и чтение данных из хранилища. Поток ввода вывода обрабатывает последовательности символов ASCII, но двоичный объект данных в формате эффективных, неизбыточной обрабатывает архив.  
  
 Необходимо создать [CFile](../../mfc/reference/cfile-class.md) объекта перед созданием `CArchive` объекта. Кроме того необходимо убедиться, что архив загрузка или сохранение состояния совместим с режим открытия файла. Существует ограничение в один архив active каждого файла.  
  
 При построении `CArchive` объекта, присоедините его к объекту класса `CFile` (или производный класс), представляющий открытый файл. Можно также указать ли архив будет использоваться для загрузки и сохранения. Объект `CArchive` объекта может обрабатывать не только простые типы, но объекты [CObject](../../mfc/reference/cobject-class.md)-производные классы, предназначенные для сериализации. Сериализуемый класс обычно имеет `Serialize` функция-член, который обычно использует [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макросов, как описано в разделе класса `CObject`.  
  
 Перегруженные извлечения ( ** >> **) и вставки ( ** << **) операторы — это удобный архив программные интерфейсы, которые поддерживают обоих типов-примитивов и `CObject`-производные классы.  
  
 `CArchive`также поддерживает программирование с помощью классов MFC Windows Sockets [CSocket](../../mfc/reference/csocket-class.md) и [CSocketFile](../../mfc/reference/csocketfile-class.md). [IsBufferEmpty](#isbufferempty) об использовании поддерживает функции-члена.  
  
 Дополнительные сведения о `CArchive`, см. в статьях [сериализации](../../mfc/serialization-in-mfc.md) и [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CArchive`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="a-nameaborta--carchiveabort"></a><a name="abort"></a>CArchive::Abort  
 Эта функция вызывается для закрытия архив без создания исключения.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Примечания  
 **CArchive** обычно вызывает деструктор **закрыть**, который будут удалены все данные, которые не были сохранены с соответствующими `CFile` объекта. Это может привести к исключениям.  
  
 При перехвате исключения, рекомендуется использовать **прервать**, так что уничтожения `CArchive` объекта не привести к возникновению других исключений. При обработке исключений, `CArchive::Abort` не будет вызывать исключение при сбое, поскольку, в отличие от [CArchive::Close](#close), **прервать** игнорирует ошибки.  
  
 Если вы использовали **новый** выделить `CArchive` объекта в куче, необходимо удалить его после закрытия файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CArchive::WriteClass](#writeclass).  
  
##  <a name="a-namecarchivea--carchivecarchive"></a><a name="carchive"></a>CArchive::CArchive  
 Создает `CArchive` и указывает, является ли он будет использоваться для загрузки или сохранения объектов.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pFile`  
 Указатель на `CFile` объект, являющийся первичным источником или назначением постоянных данных.  
  
 `nMode`  
 Флаг, указывающий, будут ли объекты загружаются из или хранящихся в архив. `nMode` Параметр должен иметь одно из следующих значений:  
  
- **CArchive::load** загружает данные из архива. Требуется только `CFile` разрешение на чтение.  
  
- **CArchive::store** сохраняет данные в архив. Требуется `CFile` разрешение на запись.  
  
- **CArchive::bNoFlushOnDelete** предотвращает автоматический вызов архив `Flush` при вызове деструктора архива. Если установлен этот флаг, вы несете ответственность за явного вызова **закрыть** перед вызовом деструктора. Если этого не сделать, данные будут повреждены.  
  
 `nBufSize`  
 Целое число, указывающее размер буфера внутреннего файла в байтах. Обратите внимание, что размер буфера по умолчанию равен 4 096 байт. Если вы регулярно архивировать большие объекты, можно улучшить производительность при использовании большего размера буфера, кратной размеру буфера файла.  
  
 `lpBuf`  
 Необязательный указатель на буфер, предоставленный пользователем размера `nBufSize`. Если этот параметр не задан, архив выделяет буфер в локальной куче и освобождает его при уничтожении объекта. Архив не позволяет освободить буфер, предоставленный пользователем.  
  
### <a name="remarks"></a>Примечания  
 Эта спецификация нельзя изменить после создания архива.  
  
 Вы не можете использовать `CFile` операций изменять состояния файла до закрытия архива. Все такие операции приведет к повреждению целостности архива. Доступ к положение указателя файла в любой момент во время сериализации, получая объект файла архива из [GetFile](#getfile) функция-член, а затем с помощью [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) функции. Следует вызвать [CArchive::Flush](#flush) перед получением позиция указателя файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#12;](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="a-nameclosea--carchiveclose"></a><a name="close"></a>CArchive::Close  
 Очищает все данные, оставшиеся в буфере, закрывает архива и отключает из файла архива.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Дальнейшие операции архива не допускаются. После закрытия архив, можно создать другой архив в том же файле, или можно закрыть файл.  
  
 Функция-член **закрыть** гарантирует, что все данные, передаваемые в файл из архива и делает архив недоступной. Для завершения передачи файла на носитель, необходимо сначала использовать [CFile::Close](../../mfc/reference/cfile-class.md#close) и затем уничтожить `CFile` объекта.  
  
### <a name="example"></a>Пример  
  В примере показано [CArchive::WriteString](#writestring).  
  
##  <a name="a-nameflusha--carchiveflush"></a><a name="flush"></a>CArchive::Flush  
 Вызывает запись данных, остающихся в буфере для записи в файл архива.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член `Flush` гарантирует, что все данные передаются из архива в файл. Необходимо вызвать [CFile::Close](../../mfc/reference/cfile-class.md#close) для завершения передачи файла на носитель.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#13;](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="a-namegetfilea--carchivegetfile"></a><a name="getfile"></a>CArchive::GetFile  
 Возвращает `CFile` указатель на объект для этого архива.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный указатель на `CFile` объект.  
  
### <a name="remarks"></a>Примечания  
 Необходимо очистить перед использованием архив `GetFile`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#14;](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="a-namegetobjectschemaa--carchivegetobjectschema"></a><a name="getobjectschema"></a>CArchive::GetObjectSchema  
 Вызывайте эту функцию из `Serialize` функции, чтобы определить версию объекта, который был десериализован.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Во время десериализации версию объекта чтения.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции действителен только при `CArchive` загружен объект ( [CArchive::IsLoading](#isloading) возвращает ненулевое значение). Это должен быть первый вызов в `Serialize` функции и вызываемой только один раз. Возвращаемое значение ( **UINT**) -1 означает, что номер версии неизвестно.  
  
 Объект `CObject`-производный класс может использовать **VERSIONABLE_SCHEMA** вместе (с помощью побитового `OR`) с версией схемы сам (в `IMPLEMENT_SERIAL` макрос) для создания «версии объекта,» то есть объект которого `Serialize` функция-член можно прочитать несколько версий. Функциональных возможностей платформы по умолчанию (без **VERSIONABLE_SCHEMA**) является исключение, если версия совпадает.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#15;](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="a-nameisbufferemptya--carchiveisbufferempty"></a><a name="isbufferempty"></a>CArchive::IsBufferEmpty  
 Вызовите эту функцию-член для определения, пуст ли объект архив внутреннего буфера.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив буфер пуст; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляется для поддержки программирования MFC Windows Sockets класс `CSocketFile`. Необходимо использовать ее для архивирования, связанные с `CFile` объекта.  
  
 Причина использования `IsBufferEmpty` с архивом, связанные с `CSocketFile` объект является то, что буфера архива может содержать более одного сообщения или записи. После получения одного сообщения, следует использовать `IsBufferEmpty` для управления циклом, по-прежнему получение данных, пока буфер пуст. Дополнительные сведения см. в разделе [получения](../../mfc/reference/casyncsocket-class.md#receive) функции-члена класса `CAsyncSocket`, который показывает, как использовать `IsBufferEmpty`.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="a-nameisloadinga--carchiveisloading"></a><a name="isloading"></a>CArchive::IsLoading  
 Определяет, загружается ли архив данных.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив используется в настоящее время для загрузки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивные классов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization №&16;](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="a-nameisstoringa--carchiveisstoring"></a><a name="isstoring"></a>CArchive::IsStoring  
 Определяет, является ли архив хранения данных.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив используется для хранения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивные классов.  
  
 Если `IsStoring` состояние архива не равно нулю, то его `IsLoading` состояние имеет значение 0 и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&17;](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="a-namemapobjecta--carchivemapobject"></a><a name="mapobject"></a>CArchive::MapObject  
 Вызов этой функции-члена для размещения объектов в схеме, действительно не сериализуются в файл, но, доступных для подчиненных для ссылки.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Параметры  
 `pOb`  
 Постоянный указатель для хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Например не может сериализовать документ, но будет сериализовать элементы, которые являются частью документа. Путем вызова `MapObject`, разрешить эти элементы или подчиненные объекты, ссылка на документ. Кроме того, можно сериализовать сериализованного подэлементы их `m_pDocument` назад указателя.  
  
 Можно вызвать `MapObject` при сохранения и загрузки из `CArchive` объекта. `MapObject`Добавляет указанный объект в структурах внутренних данных обслуживается `CArchive` объекта во время сериализации и десериализации, но в отличие от [ReadObject](#readobject) и [WriteObject](#writeobject)**,** не вызывает сериализации объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&18;](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization&19;](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization&20;](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization&#21;](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="a-namempdocumenta--carchivempdocument"></a><a name="m_pdocument"></a>CArchive::m_pDocument  
 Значение **NULL** по умолчанию, это указатель на **CDocument** может быть задано пользователем `CArchive` экземпляра желания.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Примечания  
 Общее использование этого указателя — для передачи дополнительной информации о процессе сериализации для сериализации всех объектов. Это достигается путем инициализации указатель с документом ( **CDocument**-производный класс), подвергается сериализации, таким образом, объекты в документе, доступном для документа при необходимости. Этот указатель используется также `COleClientItem` объекты во время сериализации.  
  
 Задает framework `m_pDocument` документ, сериализуемый в случае, когда пользователь выполняет файл открыть или сохранить команды. При сериализации объекта связывания и внедрения (OLE) документе-контейнере не открыть файл или сохранить, необходимо явно задать `m_pDocument`. Например это делается при сериализации контейнера документа в буфер обмена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#35;](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="a-nameoperatorltlta--carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a>CArchive::operator&lt;&lt;  
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
 A `CArchive` ссылку, которая включает несколько операторов вставки в одной строке.  
  
### <a name="remarks"></a>Примечания  
 Последние две версии выше, для хранения 64-разрядных целых чисел.  
  
 Если вы использовали `IMPLEMENT_SERIAL` макрос в реализации класса, а затем оператор вставки, перегруженные для `CObject` вызывает защищенный **WriteObject**. Эта функция, в свою очередь, вызывает `Serialize` функция класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) (оператор вставки<) supports diagnostic dumping and storing to an archive. supports="" diagnostic="" dumping="" and="" storing="" to="" an=""></) supports diagnostic dumping and storing to an archive.>  
  
### <a name="example"></a>Пример  
 В этом примере показано использование `CArchive` оператора вставки < with="" the=""> `int` и `long` типов.  
  
 [!code-cpp[NVC_MFCSerialization&#31;](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере 2 показано использование `CArchive` оператора вставки < with="" the=""> `CStringT` типа.  
  
 [!code-cpp[NVC_MFCSerialization&#32;](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="a-nameoperatorgtgta--carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a>CArchive::operator&gt;&gt;  
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
 A `CArchive` ссылку, которая включает несколько операторов извлечения в одной строке.  
  
### <a name="remarks"></a>Примечания  
 Последние две версии выше, специально для загрузки 64-разрядных целых чисел.  
  
 Если вы использовали `IMPLEMENT_SERIAL` макрос в реализации класса, то операторы извлечения, перегруженные для `CObject` вызывать защищенный **ReadObject** функция (указатель ненулевое значение класса во время выполнения). Эта функция, в свою очередь, вызывает `Serialize` функция класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) оператор извлечения (>) поддерживает загрузку из архива.  
  
### <a name="example"></a>Пример  
 В этом примере показано использование `CArchive` оператор извлечения >> с `int` типа.  
  
 [!code-cpp[NVC_MFCSerialization&#33;](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере показано использование `CArchive` операторы вставки и извлечения \< и >> с `CStringT` типа.  
  
 [!code-cpp[NVC_MFCSerialization&#34;](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="a-namereada--carchiveread"></a><a name="read"></a>CArchive::Read  
 Считывает указанное число байтов из архива.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на буфер, предоставленные пользователем, получающего данные, считанные из архива.  
  
 `nMax`  
 Целое число без знака указав число байтов, считываемых из архива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число без знака, содержащее число фактически считанных байтов. Если возвращаемое значение меньше запрошенного числа, был достигнут конец файла. Исключение не возникает при условии конечного файла.  
  
### <a name="remarks"></a>Примечания  
 Архив не распознает байты.  
  
 Можно использовать **чтения** функции-члена в пределах вашего `Serialize` функцию для считывания обычные структуры, которые содержатся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#24;](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="a-namereadclassa--carchivereadclass"></a><a name="readclass"></a>CArchive::ReadClass  
 Вызовите эту функцию-член для чтения ссылку на класс с ранее сохраненным [WriteClass](#writeclass).  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pClassRefRequested`  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует ссылка на класс в запросе. Может быть **NULL**.  
  
 `pSchema`  
 Указатель на схемы класса во время выполнения, сохраненные ранее.  
  
 `pObTag`  
 Число, которое ссылается на уникальный тег объекта. Используется внутренними механизмами реализацию [ReadObject](#readobject). Доступные для расширенного программирования `pObTag` обычно должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Если `pClassRefRequested` не **NULL**, `ReadClass` проверяет, что информация о классе архивные совместимость с класса среды выполнения. Если он не совместим, `ReadClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае — `ReadClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Если `pSchema` — **NULL**, схеме хранимых класса можно получить, вызвав [CArchive::GetObjectSchema](#getobjectschema); в противном случае — ** \* ** `pSchema` будет содержать схемы класса во время выполнения, который ранее был сохранен.  
  
 Можно использовать [SerializeClass](#serializeclass) вместо `ReadClass`, который обрабатывает чтения и записи ссылки на класс.  
  
### <a name="example"></a>Пример  
  В примере показано [CArchive::WriteClass](#writeclass).  
  
##  <a name="a-namereadobjecta--carchivereadobject"></a><a name="readobject"></a>CArchive::ReadObject  
 Считывает данные объектов из архива и создает объект соответствующего типа.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Параметры  
 `pClass`  
 Постоянный указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует объекту, предполагается, что для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CObject](../../mfc/reference/cobject-class.md) указатель, который должен быть безопасно приведен правильный производного класса с помощью [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается `CArchive` извлечения ( ** >> **) перегруженный оператор для [CObject](../../mfc/reference/cobject-class.md) указателя. **ReadObject**, в свою очередь, вызывает `Serialize` функция архивные класса.  
  
 Если указать ненулевое `pClass` параметр, получаемый при [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос, а затем функция проверяет архивные объекта класса во время выполнения. Это предполагает, что вы использовали `IMPLEMENT_SERIAL` макрос в реализации класса.  
  
### <a name="example"></a>Пример  
  В примере показано [CArchive::WriteObject](#writeobject).  
  
##  <a name="a-namereadstringa--carchivereadstring"></a><a name="readstring"></a>CArchive::ReadString  
 Вызовите эту функцию-член для чтения текстовых данных в буфер из файла, связанного с `CArchive` объекта.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `rString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) после чтения из файла, связанного с объектом CArchive, содержащий результирующие строки.  
  
 `lpsz`  
 Задает указатель на пользовательские буфера, который будет принимать строку текста с символом null.  
  
 `nMax`  
 Указывает максимальное число считываемых символов. Должна быть одна меньше, чем размер *lpsz* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В версию, которая возвращает **BOOL**, **TRUE** в случае успешного выполнения; **FALSE** в противном случае.  
  
 В версию, которая возвращает `LPTSTR`, указатель на буфер, содержащий текстовые данные; **NULL** Если был достигнут конец файла.  
  
### <a name="remarks"></a>Примечания  
 В версии этой функции `nMax` параметр буфера будет достигать ограничение `nMax` - 1 символов. Чтение остановлена с помощью пары перевода строки возврата каретки. Всегда удаляются конечные символы новой строки. В любом случае добавляется символ null («\0»).  
  
 [CArchive::Read](#read) также доступна для ввода в текстовом режиме, но не завершает работу на пару перевода строки возврата каретки.  
  
### <a name="example"></a>Пример  
  В примере показано [CArchive::WriteString](#writestring).  
  
##  <a name="a-nameserializeclassa--carchiveserializeclass"></a><a name="serializeclass"></a>CArchive::SerializeClass  
 Вызовите эту функцию-член для сохранения и загрузки сведений о версии базового класса.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 `pClassRef`  
 Указатель на объект класса во время выполнения для базового класса.  
  
### <a name="remarks"></a>Примечания  
 `SerializeClass`Считывает или записывает ссылку на класс `CArchive` объекта, в зависимости от направления `CArchive`. Используйте `SerializeClass` вместо [ReadClass](#readclass) и [WriteClass](#writeclass) — удобный способ сериализации объектов базового класса. `SerializeClass` требует меньшего объема кода и меньшее количество параметров.  
  
 Как `ReadClass`, `SerializeClass` проверяет, что информация о классе архивированные совместимость с класса среды выполнения. Если он не совместим, `SerializeClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае — `SerializeClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Используйте [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос для получения значения для `pRuntimeClass` параметр. Базовый класс должен используется [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#25;](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="a-namesetloadparamsa--carchivesetloadparams"></a><a name="setloadparams"></a>CArchive::SetLoadParams  
 Вызов `SetLoadParams` при необходимо считать большое количество `CObject`-объекты, унаследованные из архива.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Параметры  
 `nGrowBy`  
 Минимальное количество элемент слотов для выделения, если увеличение размера не требуется.  
  
### <a name="remarks"></a>Примечания  
 `CArchive`Массив нагрузки используется для разрешения ссылок на объекты, хранящиеся в архиве. `SetLoadParams`позволяет задать размер, к которому роста нагрузки массива.  
  
 Не следует вызывать `SetLoadParams` после загрузки любого объекта, или [MapObject](#mapobject) или [ReadObject](#readobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="a-namesetobjectschemaa--carchivesetobjectschema"></a><a name="setobjectschema"></a>CArchive::SetObjectSchema  
 Эта функция-член для задания объектов схемы, хранящихся в объекте архива для вызова `nSchema`.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Параметры  
 `nSchema`  
 Указывает схему объекта.  
  
### <a name="remarks"></a>Примечания  
 При следующем вызове [GetObjectSchema](#getobjectschema) возвращает значение, хранящееся в `nSchema`.  
  
 Используйте `SetObjectSchema` для расширенного управления версиями; например, если вам необходимо выполнить принудительную определенной версии должны быть прочитаны в `Serialize` функция производного класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#27;](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="a-namesetstoreparamsa--carchivesetstoreparams"></a><a name="setstoreparams"></a>CArchive::SetStoreParams  
 Используйте `SetStoreParams` при хранении большое количество `CObject`-производных объектов в архив.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Параметры  
 *nHashSize*  
 Отображает размер хэш-таблицы для указателя интерфейса. Должно быть простых чисел.  
  
 `nBlockSize`  
 Задает гранулярность выделения памяти для расширения параметров. Должно быть степенью числа 2 для повышения производительности.  
  
### <a name="remarks"></a>Примечания  
 `SetStoreParams`позволяет задать размер хэш-таблицы и размер блока карты, используемый для определения уникальных объектов в процессе сериализации.  
  
 Не следует вызывать `SetStoreParams` после хранятся все объекты, или [MapObject](#mapobject) или [WriteObject](#writeobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#26;](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="a-namewritea--carchivewrite"></a><a name="write"></a>CArchive::Write  
 Записывает указанное число байтов в архив.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на буфер, содержащий данные для записи в архив пользовательские.  
  
 `nMax`  
 Целое число, указывающее количество байтов для записи в архив.  
  
### <a name="remarks"></a>Примечания  
 Архив формате байты.  
  
 Можно использовать **записи** функции-члена в пределах вашего `Serialize` функции для записи обычного структур, содержащиеся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#23;](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="a-namewriteclassa--carchivewriteclass"></a><a name="writeclass"></a>CArchive::WriteClass  
 Используйте `WriteClass` для хранения версии и класс данных базового класса во время сериализации производного класса.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 `pClassRef`  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует ссылка на класс в запросе.  
  
### <a name="remarks"></a>Примечания  
 `WriteClass`Записывает ссылку на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для базового класса, чтобы `CArchive`. Используйте [CArchive::ReadClass](#readclass) для получения ссылок.  
  
 `WriteClass`проверяет, является ли информация о классе архивированные совместимы с вашего класса среды выполнения. Если он не совместим, `WriteClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае — `WriteClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Можно использовать [SerializeClass](#serializeclass) вместо `WriteClass`, который обрабатывает чтения и записи ссылки на класс.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#28;](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="a-namewriteobjecta--carchivewriteobject"></a><a name="writeobject"></a>CArchive::WriteObject  
 Сохраняет указанный `CObject` в архив.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Параметры  
 `pOb`  
 Постоянный указатель для хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается `CArchive` вставки ( ** << **) перегруженный оператор для `CObject`. **Метод WriteObject**, в свою очередь, вызывает `Serialize` функция архивные класса.  
  
 Необходимо использовать `IMPLEMENT_SERIAL` макрос, чтобы включить архивирование. **Метод WriteObject** записывает имя класса ASCII в архив. Это имя класса проверяется позднее во время процесса загрузки. Специальные кодировки предотвращает дублирования имя класса для нескольких объектов класса. Эта схема также предотвращает избыточное хранилище объектов, являющиеся целевыми для более чем один указатель.  
  
 Точный объект кодировку (включая наличие имени класса ASCII) метод деталь реализации и может измениться в будущих версиях библиотеки.  
  
> [!NOTE]
>  Завершите создание, удаление и обновление всех объектов, прежде чем приступать к архивировать их. При комбинировании архивирование без изменения объекта архива будет поврежден.  
  
### <a name="example"></a>Пример  
 Для определения класса `CAge`, см. пример для [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization&#29;](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="a-namewritestringa--carchivewritestring"></a><a name="writestring"></a>CArchive::WriteString  
 Используйте эту функцию-член для записи данных из буфера для файла, связанного с `CArchive` объекта.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 Задает указатель на буфер, содержащий строку текста с символом null.  
  
### <a name="remarks"></a>Примечания  
 Завершающий символ null (\0) не записываются в файл. а также автоматически записывается новая строка.  
  
 `WriteString`исключение в ответ на несколько условий, включая условия переполнения диска.  
  
 **Запись** также доступна, но заканчивается на символ null, запрошенное количество байтов записывает в файл.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization&#30;](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [CSocket-класс](../../mfc/reference/csocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)

