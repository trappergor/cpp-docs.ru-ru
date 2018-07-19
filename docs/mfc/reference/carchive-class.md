---
title: Класс CArchive | Документация Майкрософт
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
ms.openlocfilehash: 81e76347e197469e4e4fa490d4ddfc42ef0fbd71
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338086"
---
# <a name="carchive-class"></a>CArchive-класс
Позволяет сохранить сложную сеть объектов в перманентной двоичной форме (обычно диск хранения), сохраняющейся даже после удаления объектов.  
  
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
|[CArchive::Abort](#abort)|Закрывает архив без создания исключения.|  
|[CArchive::Close](#close)|Очищает незаписанных данных и отключается от `CFile`.|  
|[CArchive::Flush](#flush)|Очищает незаписанных данных из буфера архива.|  
|[CArchive::GetFile](#getfile)|Получает `CFile` указатель на объект для этого архива.|  
|[CArchive::GetObjectSchema](#getobjectschema)|Вызывается из `Serialize` функцию, чтобы определить версию объекта, который десериализуется.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Определяет ли буфер был очищен во время сокетов Windows процесс получения.|  
|[CArchive::IsLoading](#isloading)|Определяет, загружает ли архива.|  
|[CArchive::IsStoring](#isstoring)|Определяет, ли хранения архива.|  
|[CArchive::MapObject](#mapobject)|Объекты помещаются в сопоставлении, не будут сериализованы в файл, но, доступных для вложенных объектов для ссылки.|  
|[CArchive::Read](#read)|Считывает необработанные байты.|  
|[CArchive::ReadClass](#readclass)|Операции чтения, ссылку на класс ранее сохраненным с `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Вызывает объект `Serialize` функции для загрузки.|  
|[CArchive::ReadString](#readstring)|Читает одну строку текста.|  
|[CArchive::SerializeClass](#serializeclass)|Считывает или записывает ссылку на класс `CArchive` объект в зависимости от направления `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|Задает размер, к которому роста нагрузки массива. Должен вызываться перед загрузкой любого объекта, или перед `MapObject` или `ReadObject` вызывается.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Задает схему объекта, хранящееся в объекте архива.|  
|[CArchive::SetStoreParams](#setstoreparams)|Задает размер хэш-таблицы и размер блока проекцию, используемую для определения уникальных объектов в процессе сериализации.|  
|[CArchive::Write](#write)|Записывает необработанные байты.|  
|[CArchive::WriteClass](#writeclass)|Записывает ссылку на `CRuntimeClass` для `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Вызывает объект `Serialize` функции для хранения.|  
|[CArchive::WriteString](#writestring)|Выводит отдельную строку текста.|  
  
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
  
 Позже можно загрузить объекты из постоянного хранилища, восстановление их в памяти. Этот процесс внесения постоянных данных называется «сериализация».  
  
 Можно представить объектом архив в качестве своего рода двоичного потока. Как и поток ввода вывода архива связан с файлом и разрешает буферизованных записью и чтением данных из хранилища. Поток ввода вывода обрабатывает последовательности символов ASCII, но архив обрабатывает данные двоичного объекта в формате эффективных, неизбыточной.  
  
 Необходимо создать [CFile](../../mfc/reference/cfile-class.md) перед созданием `CArchive` объекта. Кроме того необходимо убедиться, что состояние загрузки или сохранения архива совместима с режима открытия файла. Существует ограничение в один архив active каждого файла.  
  
 При построении `CArchive` объекта, присоединить ее к объекту класса `CFile` (или производного класса), представляющий открытый файл. Можно также указать ли архив будет использоваться для загрузки или хранения. Объект `CArchive` объект может обрабатывать не только типы-примитивы, но и объекты [CObject](../../mfc/reference/cobject-class.md)-производные классы, предназначенные для сериализации. Сериализуемого класса обычно имеет `Serialize` функция-член оно обычно использует [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макросов, как описано в разделе класса `CObject`.  
  
 Перегруженный извлечения ( **>>**) и вставки ( **<<**) операторы — это удобный архив программные интерфейсы, поддерживающие обоих типов-примитивов и `CObject` -производные классы.  
  
 `CArchive` также поддерживает программирование с использованием классов MFC Windows Sockets [CSocket](../../mfc/reference/csocket-class.md) и [CSocketFile](../../mfc/reference/csocketfile-class.md). [IsBufferEmpty](#isbufferempty) функция-член поддерживает это использование.  
  
 Дополнительные сведения о `CArchive`, см. в статьях [сериализации](../../mfc/serialization-in-mfc.md) и [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CArchive`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="abort"></a>  CArchive::Abort  
 Вызывайте эту функцию, чтобы закрыть архива без создания исключения.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Примечания  
 `CArchive` Обычно вызывает деструктор `Close`, который записывал любые данные, которые не были сохранены в связанный `CFile` объекта. Это может вызвать исключения.  
  
 При перехвате исключения, рекомендуется использовать `Abort`, так что так `CArchive` объекта не приведут к получению исключения. При обработке исключений, `CArchive::Abort` не будет выдано исключение в случае сбоев, поскольку, в отличие от [CArchive::Close](#close), `Abort` игнорирует сбоев.  
  
 Если вы использовали **новый** выделить `CArchive` объекта в куче, а затем необходимо удалить его после закрытия файла.  
  
### <a name="example"></a>Пример  
  См. в примере [CArchive::WriteClass](#writeclass).  
  
##  <a name="carchive"></a>  CArchive::CArchive  
 Создает `CArchive` объекта и указывает ли он будет использоваться для загрузки или хранения объектов.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pFile*  
 Указатель на `CFile` объект, являющийся первичным источником или целевой постоянных данных.  
  
 *nMode*  
 Флаг, указывающий, будут ли объекты загружаются из или сохранена в архиве. *NMode* параметр должен иметь одно из следующих значений:  
  
- `CArchive::load` Загружает данные из архива. Требуется только `CFile` разрешение на чтение.  
  
- `CArchive::store` Сохраняет данные в архив. Требуется `CFile` разрешение на запись.  
  
- `CArchive::bNoFlushOnDelete` Предотвращает автоматический вызов архива `Flush` при вызове деструктора архива. Если установлен этот флаг, вы несете ответственность за явного вызова `Close` перед вызовом деструктора. Если этого не сделать, данные будут повреждены.  
  
 *nBufSize*  
 Целое число, указывающее размер буфера внутреннего файла, в байтах. Обратите внимание на то, что размер буфера по умолчанию равен 4 096 байт. Если вы регулярно архивируете больших объектов, можно улучшить производительность при использовании большего размера буфера, кратной размеру буфера файла.  
  
 */ / lpBuf*  
 Необязательным указателем на буфер, предоставленный пользователем размера *nBufSize*. Если вы не укажете этот параметр, архив выделяет буфер в локальной куче и освобождает его при уничтожении объекта. Архив не освобождает буфер, предоставленный пользователем.  
  
### <a name="remarks"></a>Примечания  
 Эта спецификация нельзя изменить после создания архива.  
  
 Вы не можете использовать `CFile` операций изменять состояние файла, до закрытия архива. Любой такой операции будет нарушить целостность архива. Доступ к положение указателя файла в любое время во время сериализации, получив объект файла архива из [GetFile](#getfile) функция-член, а затем с помощью [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) функции . Следует вызывать [CArchive::Flush](#flush) перед получением положение указателя файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>  CArchive::Close  
 Очищает любые данные, остающихся в буфере, закрывает архива и отключает из файла архива.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные операции в архив не разрешены. После того как вы закроете архив, можно создать другой архив для одного файла, или можно закрыть файл.  
  
 Функция-член `Close` гарантирует, что все данные передаются из архива в файл, и он делает недоступной архива. Чтобы завершить операцию передачи из файла среду хранения, сначала необходимо использовать [CFile::Close](../../mfc/reference/cfile-class.md#close) и дальнейшему `CFile` объекта.  
  
### <a name="example"></a>Пример  
  См. в примере [CArchive::WriteString](#writestring).  
  
##  <a name="flush"></a>  CArchive::Flush  
 Заставляет все данные, остающихся в буфере архив для записи в файл.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член `Flush` гарантирует, что все данные передаются из архива в файл. Необходимо вызвать [CFile::Close](../../mfc/reference/cfile-class.md#close) выполнить передачу из файла в среде хранения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>  CArchive::GetFile  
 Получает `CFile` указатель на объект для этого архива.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Постоянный указатель на `CFile` объект используется.  
  
### <a name="remarks"></a>Примечания  
 Необходимо записать архив перед использованием `GetFile`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema  
 Вызывайте эту функцию из `Serialize` функцию, чтобы определить версию, в настоящее время Десериализуемый объект.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Во время десериализации, версию считываемого объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции является только действительным, если `CArchive` загружается объект ( [CArchive::IsLoading](#isloading) возвращает ненулевое значение). Он должен быть первый вызов в `Serialize` функции и вызываемой только один раз. Возвращаемое значение (целое число без знака) -1 указывает, что номер версии неизвестно.  
  
 Объект `CObject`-производный класс может использовать в сочетании VERSIONABLE_SCHEMA (с помощью побитового **или**) с версией схемы, сам (в IMPLEMENT_SERIAL-макрос) для создания «обновляемого объекта,» то есть объект которого `Serialize` функция-член может считывать несколько версий. Функциональные возможности платформы по умолчанию (без VERSIONABLE_SCHEMA) является исключение, если версия совпадает.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty  
 Вызывайте эту функцию члена, чтобы определить, является ли пустым внутреннего буфера объекта архива.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив буфер пуст; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция предоставляется для поддержки программирования с помощью класса MFC Windows Sockets `CSocketFile`. Необходимо использовать его с архивом, связанные с `CFile` объекта.  
  
 Причина использования `IsBufferEmpty` с архив, связанные с `CSocketFile` объект является то, что буфер архива может содержать более одного сообщения или записи. После получения одно сообщение, следует использовать `IsBufferEmpty` для управления циклом, по-прежнему получает данные, пока буфер пуст. Дополнительные сведения см. в разделе [Receive](../../mfc/reference/casyncsocket-class.md#receive) функция-член класса `CAsyncSocket`, который показывает, как использовать `IsBufferEmpty`.  
  
 Дополнительные сведения см. в разделе [Windows Sockets: с помощью сокетов с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isloading"></a>  CArchive::IsLoading  
 Определяет, загружается ли архив данных.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив используется для загрузки; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивные классов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>  CArchive::IsStoring  
 Определяет, хранит ли архив данных.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если архив используется для хранения; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `Serialize` функции архивные классов.  
  
 Если `IsStoring` состояние архива не равно нулю, а затем его `IsLoading` status имеет значение 0 и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>  CArchive::MapObject  
 Вызовите эту функцию-член для размещения объектов в карте, действительно не сериализуются в файл, но, доступных для вложенных объектов для ссылки.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Параметры  
 *почтовый ящик*  
 Постоянный указатель на хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Например не может сериализовать документ, но будет сериализовать элементы, которые являются частью документа. Путем вызова `MapObject`, разрешить элементы, или подчиненных объектов, ссылка на документ. Кроме того, можно сериализовать сериализованный подэлементы их *m_pDocument* обратного указателя.  
  
 Можно вызвать `MapObject` при сохранения и загрузки из `CArchive` объекта. `MapObject` Добавляет указанный объект в структурах внутренних данных, поддерживаемых `CArchive` объекта во время сериализации и десериализации, но в отличие от [ReadObject](#readobject) и [WriteObject](#writeobject), он не вызывает сериализация объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>  CArchive::m_pDocument  
 Значение NULL по умолчанию, это указатель на `CDocument` можно задать, к любому пользователю `CArchive` экземпляра желания.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Примечания  
 Распространенным вариантом применения этого указателя — для передачи дополнительных сведений об процесс сериализации для сериализации всех объектов. Это достигается путем инициализации указатель с документом ( `CDocument`-производного класса), подвергается сериализации, в том виде, в рамках документа доступно документа, при необходимости. Этот указатель используется также `COleClientItem` объектов во время сериализации.  
  
 Наборы framework *m_pDocument* в документ, сериализуемый в случае, когда пользователь отправляет файл открыть или сохранить команды. При сериализации документ интерфейс OLE и связывание объекта контейнера для причинам, отличным от открытия файла или сохранить, необходимо явно задать *m_pDocument*. Например это делается при сериализации документа-контейнера в буфер обмена.  
  
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
 Две последние версии выше, в частности, для хранения 64-разрядных целых чисел.  
  
 Если вы использовали IMPLEMENT_SERIAL-макрос в реализации класса, то оператор вставки перегружается для `CObject` вызывает защищенный `WriteObject`. Эта функция, в свою очередь, вызывает `Serialize` функции класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) оператор вставки (<<) поддерживает диагностики создания дампа и хранение в архив.  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется использование `CArchive` оператор вставки << с **int** и **long** типов.  
  
 [!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере 2 показано использование `CArchive` оператор вставки << с `CStringT` типа.  
  
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
 Две последние версии выше, являются специально для загрузки 64-разрядных целых чисел.  
  
 Если вы использовали IMPLEMENT_SERIAL-макрос в реализации класса, то перегруженные операторы извлечения для `CObject` вызова защищенного `ReadObject` функция (указатель ненулевое класс времени выполнения). Эта функция, в свою очередь, вызывает `Serialize` функции класса.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) оператор извлечения (>>) поддерживает загрузку из архива.  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется использование `CArchive` оператор извлечения >> с **int** типа.  
  
 [!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется использование `CArchive` операторов вставки и извлечения <\< и >> с `CStringT` типа.  
  
 [!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>  CArchive::Read  
 Считывает указанное число байтов из архива.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 */ / lpBuf*  
 Указатель на буфер, предоставленный пользователем, который принимает данные, считанные из архива.  
  
 *Nмакс.*  
 Целое число без знака указав число байтов для чтения из архива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число без знака, содержащее число фактически считанных байтов. Если возвращаемое значение меньше запрошенного числа, был достигнут конец файла. Исключение не создается при условии конец файла.  
  
### <a name="remarks"></a>Примечания  
 Архив не интерпретирует байты.  
  
 Можно использовать `Read` функция-член в рамках вашей `Serialize` функцию для считывания обычные структуры, которые содержатся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>  CArchive::ReadClass  
 Эта функция-член для чтения ссылка на класс, сохраненные ранее с помощью вызова [WriteClass](#writeclass).  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRefRequested*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует запросу ссылки на класс. Может иметь значение NULL.  
  
 *pSchema*  
 Указатель на схему класса во время выполнения, сохраненные ранее.  
  
 *pObTag*  
 Число, которое ссылается на уникальный тег объекта. Используется системой реализация [ReadObject](#readobject). Предоставляются дополнительные программирования. *pObTag* обычно должен иметь значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Если *pClassRefRequested* не равно NULL, `ReadClass` проверяет, что сведения о классе архивные совместим с вашего класса среды выполнения. Если он не подходит, `ReadClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае `ReadClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Если *pSchema* имеет значение NULL, со схемой хранимой класса можно получить, вызвав [CArchive::GetObjectSchema](#getobjectschema); в противном случае **\**** pSchema* будет содержит схему класса во время выполнения, который был ранее сохранен.  
  
 Можно использовать [SerializeClass](#serializeclass) вместо `ReadClass`, которая обрабатывает чтение и запись ссылки на класс.  
  
### <a name="example"></a>Пример  
  См. в примере [CArchive::WriteClass](#writeclass).  
  
##  <a name="readobject"></a>  CArchive::ReadObject  
 Считывает объект данных из архива и создает объект нужного типа.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Параметры  
 *pClass*  
 Постоянный указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует объекту, предполагается, что для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CObject](../../mfc/reference/cobject-class.md) указатель, который должен быть безопасно приведен к правильным производного класса с помощью [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается обычно `CArchive` извлечения ( **>>**) перегрузка оператора для [CObject](../../mfc/reference/cobject-class.md) указатель. `ReadObject`, в свою очередь, вызывает `Serialize` функции архивные класса.  
  
 Если указать ненулевое значение аргумента *pClass* параметр, который получается путем [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос, а затем функция проверяет класс времени выполнения архивные объекта. Это предполагает, что вы использовали IMPLEMENT_SERIAL-макрос в реализации класса.  
  
### <a name="example"></a>Пример  
  См. в примере [CArchive::WriteObject](#writeobject).  
  
##  <a name="readstring"></a>  CArchive::ReadString  
 Вызовите эта функция-член для чтения данных текст в буфер из файла, связанного с `CArchive` объекта.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *rString*  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) после чтения из файла, связанного с объектом CArchive, содержащий результирующие строки.  
  
 *lpsz*  
 Задает указатель на буфер, предоставленные пользователем, который будет принимать строку текста с завершающим нулем.  
  
 *Nмакс.*  
 Указывает максимальное количество символов для чтения. Должна быть одна меньше, чем размер *lpsz* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В версию, которая возвращает логическое значение, значение TRUE, если выполнение прошло успешно; Значение FALSE в противном случае.  
  
 В версию, которая возвращает `LPTSTR`, указатель на буфер, содержащий текстовые данные; Значение NULL, если достигнут конец файла.  
  
### <a name="remarks"></a>Примечания  
 В версии функции-члена с *Nмакс.* параметра буфера будет хранить до ограничение на число *Nмакс.* - 1 символов. Чтение останавливается с помощью пары перевода строки возврата каретки. Всегда удаляются конечные символы новой строки. В любом случае добавляется символ null («\0»).  
  
 [CArchive::Read](#read) также доступна для входных данных в текстовом режиме, но не завершает работу на пару перевода строки возврата каретки.  
  
### <a name="example"></a>Пример  
  См. в примере [CArchive::WriteString](#writestring).  
  
##  <a name="serializeclass"></a>  CArchive::SerializeClass  
 Вызовите эту функцию-член для хранения и загрузить информацию о версии базового класса.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRef*  
 Указатель на объект класса среды выполнения для базового класса.  
  
### <a name="remarks"></a>Примечания  
 `SerializeClass` Считывает или записывает ссылку на класс `CArchive` объекта, в зависимости от направления `CArchive`. Используйте `SerializeClass` вместо [ReadClass](#readclass) и [WriteClass](#writeclass) как удобный способ сериализации объектов базового класса; `SerializeClass` требует меньше кода и меньше параметров.  
  
 Как и `ReadClass`, `SerializeClass` проверяет, что сведения о классе архивные совместим с вашего класса среды выполнения. Если он не подходит, `SerializeClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Класс среды выполнения необходимо использовать [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) и [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial); в противном случае `SerializeClass` вызовет [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Используйте [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) макрос для получения значения для *pRuntimeClass* параметра. Необходимо использовать базовый класс [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>  CArchive::SetLoadParams  
 Вызовите `SetLoadParams` когда нужно считывать большое количество `CObject`-объектов, производных из архива.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Параметры  
 *nGrowBy*  
 Минимальное число слотов элемент для выделения, если увеличение размера не требуется.  
  
### <a name="remarks"></a>Примечания  
 `CArchive` Массив нагрузки используется для разрешения ссылок на объекты, хранящиеся в архиве. `SetLoadParams` позволяет задать размер, к которому роста нагрузки массива.  
  
 Не следует вызывать `SetLoadParams` после загрузки любого объекта, или после [MapObject](#mapobject) или [ReadObject](#readobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema  
 Эта функция-член для задания схемы объекта, который хранится в объекте архив, чтобы вызвать *nSchema*.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Параметры  
 *nSchema*  
 Указывает схемы объекта.  
  
### <a name="remarks"></a>Примечания  
 Следующий вызов [GetObjectSchema](#getobjectschema) возвращает значение, хранящееся в *nSchema*.  
  
 Используйте `SetObjectSchema` для расширенной управления версиями; например, при нужно, чтобы определенная версия считывать `Serialize` функция производного класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>  CArchive::SetStoreParams  
 Используйте `SetStoreParams` при сохранении большое количество `CObject`-производных объектов в архив.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Параметры  
 *nHashSize*  
 Сопоставляет размер хэш-таблицы для указателя интерфейса. Должно быть простое число.  
  
 *nBlockSize*  
 Указывает гранулярность выделения памяти для расширения параметров. Должно быть степенью числа 2 для повышения производительности.  
  
### <a name="remarks"></a>Примечания  
 `SetStoreParams` позволяет задать размер хэш-таблицы и размер блока проекцию, используемую для определения уникальных объектов в процессе сериализации.  
  
 Не следует вызывать `SetStoreParams` после хранятся все объекты, или [MapObject](#mapobject) или [WriteObject](#writeobject) вызывается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>  CArchive::Write  
 Записывает указанное число байтов в архив.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 */ / lpBuf*  
 Указатель на буфер, содержащий данные для записи в архив предоставленное пользователем.  
  
 *Nмакс.*  
 Целое число, указывающее количество байтов для записи в архив.  
  
### <a name="remarks"></a>Примечания  
 Архив не форматирует байты.  
  
 Можно использовать `Write` функция-член в рамках вашей `Serialize` функции для записи обычных структуры, содержащиеся в объектах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>  CArchive::WriteClass  
 Используйте `WriteClass` для хранения класс сведения о версии и базового класса во время сериализации производного класса.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Параметры  
 *pClassRef*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, которая соответствует запросу ссылки на класс.  
  
### <a name="remarks"></a>Примечания  
 `WriteClass` Записывает ссылку на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для базового класса, чтобы `CArchive`. Используйте [CArchive::ReadClass](#readclass) для извлечения ссылки.  
  
 `WriteClass` проверяет, что сведения о классе архивные совместим с вашего класса среды выполнения. Если он не подходит, `WriteClass` вызовет [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
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
 Постоянный указатель на хранимого объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается обычно `CArchive` вставки ( **<<**) перегрузка оператора для `CObject`. `WriteObject`, в свою очередь, вызывает `Serialize` функции архивные класса.  
  
 IMPLEMENT_SERIAL-макрос необходимо использовать для включения архивации. `WriteObject` Записывает имя класса ASCII в архив. Это имя класса проверяется позже в процессе загрузки. Специальные кодировки предотвращает ненужные повторения имени класса для нескольких объектов класса. Эта схема также предотвращает избыточное хранилище объектов, являющихся целевыми объектами более одного указателя.  
  
 Точный объект (в том числе наличие имени класса ASCII) метод кодирования деталь реализации и может измениться в будущих версиях библиотеки.  
  
> [!NOTE]
>  Завершите создание, удаление и обновление всех объектов, прежде чем приступать к их архивировать. Если смешать архивирование без изменения объекта будут повреждены архива.  
  
### <a name="example"></a>Пример  
 Для определения класса `CAge`, см. в примере [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>  CArchive::WriteString  
 Использовать эту функцию-член для записи данных из буфера к файлу, связанному с `CArchive` объекта.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 *lpsz*  
 Определяет указатель на буфер, содержащий строку текста с завершающим нулем.  
  
### <a name="remarks"></a>Примечания  
 Завершающий нуль-символ («\0») не записывается в файл; а также автоматически записывается новой строки.  
  
 `WriteString` вызывает исключение в ответ на несколько условий, включая условия переполнения диска.  
  
 `Write` также доступна, но вместо того чтобы останавливаясь на символ null, он записывает запрошенное число байт в файл.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFile](../../mfc/reference/cfile-class.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)   
 [Класс CSocket](../../mfc/reference/csocket-class.md)   
 [Класс CSocketFile](../../mfc/reference/csocketfile-class.md)
