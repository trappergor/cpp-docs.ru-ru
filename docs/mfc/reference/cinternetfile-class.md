---
title: "Класс CInternetFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile class
- Internet files
- Internet files, CInternetFile class
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e1d6227ebd642025e6b00019518d29080cf0454
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetfile-class"></a>Класс CInternetFile
Разрешает доступ к файлам на удаленных системах, использующих протоколы Интернета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|Создает объект `CInternetFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|  
|[CInternetFile::Close](#close)|Закрывает `CInternetFile` и освобождает его ресурсы.|  
|[CInternetFile::Flush](#flush)|Очищает содержимое буфера записи и гарантирует, что данные в памяти записывается на целевом компьютере.|  
|[CInternetFile::GetLength](#getlength)|Возвращает размер файла.|  
|[CInternetFile::Read](#read)|Считывает число указанного числа байтов.|  
|[CInternetFile::ReadString](#readstring)|Считывает поток символов.|  
|[CInternetFile::Seek](#seek)|Перемещает указатель на открытый файл.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Задает размер буфера, в которой будут считываться данные.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Задает размер буфера будут записаны данные.|  
|[CInternetFile::Write](#write)|Записывает число указанного числа байтов.|  
|[CInternetFile::WriteString](#writestring)|Записывает строку, завершающуюся значением null в файл.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Оператор приведения для Интернет-дескриптор.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Дескриптор файла.|  
  
## <a name="remarks"></a>Примечания  
 Предоставляет базовый класс для [CHttpFile](../../mfc/reference/chttpfile-class.md) и [CGopherFile](../../mfc/reference/cgopherfile-class.md) файл классов. Никогда не создавать `CInternetFile` напрямую. Создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Можно также создавать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 `CInternetFile` Функции-члены **откройте**, `LockRange`, `UnlockRange`, и `Duplicate` не реализована для `CInternetFile`. При вызове этих функций для `CInternetFile` объект, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CInternetFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="a-nameaborta--cinternetfileabort"></a><a name="abort"></a>CInternetFile::Abort  
 Закрывает файл, связанный с данным объектом и он становится недоступным для чтения или записи.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Примечания  
 Файл не закрыт перед удалением объекта, деструктор закрывается автоматически.  
  
 При обработке исключений, **прервать** отличается от [закрыть](#close) в двух важных моментах. Во-первых, **прервать** функция не вызывает исключение при сбое, так как он игнорирует ошибки. Во-вторых, **прервать** не **ASSERT** Если файл не был открыт или закрыт ранее.  
  
##  <a name="a-namecinternetfilea--cinternetfilecinternetfile"></a><a name="cinternetfile"></a>CInternetFile::CInternetFile  
 Эта функция-член вызывается `CInternetFile` создается объект.  
  
```  
CInternetFile(
    HINTERNET hFile,  
    LPCTSTR pstrFileName,  
    CInternetConnection* pConnection,  
    BOOL bReadMode);

 
CInternetFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrFileName,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext,  
    BOOL bReadMode);
```  
  
### <a name="parameters"></a>Параметры  
 `hFile`  
 Дескриптор файла Интернета.  
  
 `pstrFileName`  
 Указатель на строку, содержащую имя файла.  
  
 `pConnection`  
 Указатель на [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) объекта.  
  
 *bReadMode*  
 Указывает, является ли файл только для чтения.  
  
 `hSession`  
 Дескриптор для Интернет-сеанс.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера.  
  
 `dwContext`  
 Идентификатор контекста для `CInternetFile` объекта. В разделе [основы WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CInternetFile` напрямую. Создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Можно также создавать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="a-nameclosea--cinternetfileclose"></a><a name="close"></a>CInternetFile::Close  
 Закрывает `CInternetFile` и освобождает его ресурсы.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл был открыт для записи, имеется неявный вызов [Flush](#flush) для гарантии, что все буферизованные данные записываются на узел. Следует вызвать **закрыть** после использования файла.  
  
##  <a name="a-nameflusha--cinternetfileflush"></a><a name="flush"></a>CInternetFile::Flush  
 Вызовите эту функцию-член для записи содержимого буфера записи на диск.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `Flush` для гарантии, что все данные в памяти на самом деле были записаны на конечный компьютер и гарантировать завершения транзакции с хост-компьютера. `Flush`действует только на `CInternetFile` объектов открыть для записи.  
  
##  <a name="a-namegetlengtha--cinternetfilegetlength"></a><a name="getlength"></a>CInternetFile::GetLength  
 Возвращает размер файла.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="a-namemhfilea--cinternetfilemhfile"></a><a name="m_hfile"></a>CInternetFile::m_hFile  
 Дескриптор файла, связанного с данным объектом.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="a-nameoperatorhinterneta--cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetFile::operator HINTERNET  
 Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернета.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="a-namereada--cinternetfileread"></a><a name="read"></a>CInternetFile::Read  
 Вызывайте эту функцию-член для чтения заданного числа байтов (`nCount`) в указанных областях памяти (начиная со значения параметра `lpvBuf`).  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на адрес в памяти, по которому считываются данные из файла.  
  
 `nCount`  
 Число записываемых байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество байтов, переданных в буфер. Если достигнут конец файла, возвращаемое значение может быть меньше значения параметра `nCount`.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает число фактически считанных байтов, которое может быть меньше значения `nCount`, если файл закончился. Если произошла ошибка при чтении файла, эта функция создает исключение [CInternetException](../../mfc/reference/cinternetexception-class.md) , описывающий ошибку. Обратите внимание, что чтение после завершения файла не является ошибкой и не может быть причиной выдачи исключения.  
  
 Чтобы получить все данные, приложение должно продолжать вызывать **CInternetFile::Read** пока метод возвращает ноль.  
  
##  <a name="a-namereadstringa--cinternetfilereadstring"></a><a name="readstring"></a>CInternetFile::ReadString  
 Вызовите эту функцию-член для чтения поток символов, пока не найдет символ перевода строки.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на строку, которая получит считываемой строки.  
  
 `nMax`  
 Максимальное число символов для чтения.  
  
 `rString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, получающий чтения строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер, содержащий обычные данные, полученные из [CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта. Независимо от типа данных буфера, переданного этому методу, не выполняет любые программные манипуляции с данными (например, преобразование в Юникод), поэтому необходимо сопоставить возвращенные данные в структуру предполагается, как если бы **void\* ** типа были возвращены.  
  
 **NULL** был достигнут конец файла не считывая все данные, или, если логическое значение **FALSE** Если был достигнут конец файла не считывая все данные.  
  
### <a name="remarks"></a>Примечания  
 Функция передает результирующие строки в память, ссылается `pstr` параметр. Прекращает чтение знаков при достижении максимальное количество символов, заданные `nMax`. Буфер всегда получает конечный символ null.  
  
 При вызове метода `ReadString` без предварительного вызова функции [SetReadBufferSize](#setreadbuffersize), вы получите буфера 4096 байт.  
  
##  <a name="a-nameseeka--cinternetfileseek"></a><a name="seek"></a>CInternetFile::Seek  
 Вызовите эту функцию-член можно переместить указатель в уже открытого файла.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Параметры  
 `lOffset`  
 Смещение в байтах для перемещения указателя чтение и запись в файл.  
  
 `nFrom`  
 Относительная ссылка для смещения. Должно быть одно из следующих значений:  
  
- **CFile::begin** перемещать указатель файла `lOff` байтов вперед от начала файла.  
  
- **CFile::current** перемещать указатель файла `lOff` байт, начиная с текущей позиции в файле.  
  
- **CFile::end** перемещать указатель файла `lOff` байт в конце файла. `lOff`должно быть отрицательным для поиска в существующий файл. положительные значения выполнит поиск за концом файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый байт смещение от начала файла запрошенной позиции является допустимым; в противном случае — значение не определено и [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта создается исключение.  
  
### <a name="remarks"></a>Примечания  
 `Seek` Функция позволяет произвольный доступ к содержимому файла, перемещая указатель указанного значения, имеет абсолютного или относительного. На самом деле нет данных считывается в процессе поиска.  
  
 В настоящее время вызова функции-члена поддерживается только для данных, связанных с `CHttpFile` объектов. Не поддерживается для запросов FTP и gopher. При вызове метода `Seek` для одного из этих служб не поддерживается, он будет передавать обратно коду ошибки Win32 **ERROR_INTERNET_INVALID_OPERATION**.  
  
 При открытии файла указатель файла — со смещением 0, в начало файла.  
  
> [!NOTE]
>  С помощью `Seek` может привести к неявный вызов [Flush](#flush).  
  
### <a name="example"></a>Пример  
  См. пример реализации базового класса ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="a-namesetreadbuffersizea--cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 Эта функция члена задается размер временного буфера чтения, используемый `CInternetFile`-производный объект.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nReadSize*  
 Требуемый размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Базовые интерфейсы API WinInet не выполняют буферизацию, поэтому выберите размер буфера, который позволяет приложению считывать данные эффективно, независимо от объема данных для чтения. Если при каждом вызове функции [чтения](#read) обычно включает в себя большой aount данных (например, четырьмя или более килобайт), нет необходимости буфера. Тем не менее при вызове **чтения** для получения небольших объемов данных, или если вы используете [ReadString](#readstring) для чтения отдельных строк во время чтения буфера улучшает производительность приложения.  
  
 По умолчанию `CInternetFile` объект не имеет буферизации для чтения. Если вызывается функция-член, необходимо убедиться, что файл был открыт для доступа на чтение.  
  
 Можно увеличить размер буфера в любое время, но сжатие буфер не будет действовать. При вызове метода [ReadString](#readstring) без предварительного вызова метода `SetReadBufferSize`, вы получите буфера 4096 байт.  
  
##  <a name="a-namesetwritebuffersizea--cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 Вызовите эту функцию-член для установки размера временной записи буфера, используемого `CInternetFile`-производный объект.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nWriteSize*  
 Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Базовые интерфейсы API WinInet не выполняют буферизацию, поэтому выберите размер буфера, который позволяет приложению записывать данные эффективно независимо от объема записываемых данных. Если при каждом вызове функции [записи](#write) обычно подразумевает большой объем данных (например, четырьмя или более килобайт одновременно), нет необходимости буфера. Тем не менее при вызове [запись](#write) для записи небольших объемов данных, буфер записи улучшает производительность приложения.  
  
 По умолчанию `CInternetFile` объект не имеет буферизации для записи. Если вызывается функция-член, необходимо убедиться, что файл был открыт для записи. Размер буфера записи можно изменить в любое время, но при этом неявный вызов [Flush](#flush).  
  
##  <a name="a-namewritea--cinternetfilewrite"></a><a name="write"></a>CInternetFile::Write  
 Вызов этой функции-члена для записи в памяти, `lpvBuf`, указанное число байтов, `nCount`.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на первый байт для записи.  
  
 `nCount`  
 Указывает число байтов для записи.  
  
### <a name="remarks"></a>Примечания  
 Если возникают ошибки при записи данных, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) объект, описывающий ошибку.  
  
##  <a name="a-namewritestringa--cinternetfilewritestring"></a><a name="writestring"></a>CInternetFile::WriteString  
 Эта функция записывает строку, завершающуюся значением null к соответствующему файлу.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на строку, содержащую содержимое для записи.  
  
### <a name="remarks"></a>Примечания  
 Если возникают ошибки при записи данных, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) объект, описывающий ошибку.  
  
## <a name="see-also"></a>См. также  
 [Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

