---
title: "Класс классе CInternetFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1e4b05e2aceb8fb4c8a4abed0dd6038fff6cfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cinternetfile-class"></a>Класс классе CInternetFile
Разрешает доступ к файлам на удаленных компьютерах, использующих протоколы Интернета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|Создает объект `CInternetFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|  
|[CInternetFile::Close](#close)|Закрывает `CInternetFile` и освобождает его ресурсы.|  
|[CInternetFile::Flush](#flush)|Очищает содержимое буфера записи и гарантирует, что данные в памяти записывается на целевой компьютер.|  
|[CInternetFile::GetLength](#getlength)|Возвращает размер файла.|  
|[CInternetFile::Read](#read)|Считывает число указанных байтов.|  
|[CInternetFile::ReadString](#readstring)|Считывает поток символов.|  
|[CInternetFile::Seek](#seek)|Перемещает указатель в открытом файле.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Задает размер буфера, где будет считывать данные.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Задает размер буфера, где данные будут записаны.|  
|[CInternetFile::Write](#write)|Записывает число указанных байтов.|  
|[CInternetFile::WriteString](#writestring)|Записывает в файл строку, завершающуюся символом null.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Оператор приведения для Интернет-дескриптор.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Дескриптор файла.|  
  
## <a name="remarks"></a>Примечания  
 Предоставляет базовый класс для [CHttpFile](../../mfc/reference/chttpfile-class.md) и [CGopherFile](../../mfc/reference/cgopherfile-class.md) файл классов. Никогда не создавайте `CInternetFile` объекта напрямую. Создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Можно также создавать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 `CInternetFile` Функции-члены **откройте**, `LockRange`, `UnlockRange`, и `Duplicate` не реализован для `CInternetFile`. При вызове этих функций для `CInternetFile` объекта, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CInternetFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="abort"></a>CInternetFile::Abort  
 Закрывает файл, связанный с этим объектом и он становится недоступным для чтения или записи.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.  
  
 При обработке исключений, **прервать** отличается от [закрыть](#close) в двух важных аспектах. Во-первых, **прервать** функция не вызывает исключение при сбое так как он не учитывает сбоев. Во-вторых, **прервать** не **ASSERT** Если файл не открыт или закрыт ранее.  
  
##  <a name="cinternetfile"></a>CInternetFile::CInternetFile  
 Эта функция-член вызывается, когда `CInternetFile` создан объект.  
  
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
 Идентификатор контекста для `CInternetFile` объекта. В разделе [основные сведения о WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CInternetFile` объекта напрямую. Создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Можно также создавать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>CInternetFile::Close  
 Закрывает `CInternetFile` и освобождает все ее ресурсы.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл был открыт для записи, имеется неявный вызов [Flush](#flush) гарантировать, что все буферизованные данные записываются на узел. Необходимо вызвать **закрыть** после использования файла.  
  
##  <a name="flush"></a>CInternetFile::Flush  
 Вызовите эту функцию-член, чтобы очистить содержимое буфера записи.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `Flush` для гарантии, что все данные в памяти фактически записанных на целевой компьютер и гарантировать завершения транзакции с хост-компьютера. `Flush`действует только на `CInternetFile` открытых объектов для записи.  
  
##  <a name="getlength"></a>CInternetFile::GetLength  
 Возвращает размер файла.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>CInternetFile::m_hFile  
 Дескриптор файла, связанного с данным объектом.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>CInternetFile::operator HINTERNET  
 Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернета.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>CInternetFile::Read  
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
 Функция возвращает число фактически считанных байтов, которое может быть меньше значения `nCount`, если файл закончился. Если произошла ошибка при чтении файла, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) объектом, содержащим описание ошибки. Обратите внимание, что чтение после завершения файла не является ошибкой и не может быть причиной выдачи исключения.  
  
 Чтобы гарантировать извлечение всех данных, приложение должно продолжить вызывать **CInternetFile::Read** метод, пока метод возвращает ноль.  
  
##  <a name="readstring"></a>CInternetFile::ReadString  
 Вызовите эту функцию-член для чтения поток символов, пока не найдет символ перевода строки.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на строку, которая получит прочитанная.  
  
 `nMax`  
 Максимальное число символов для чтения.  
  
 `rString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, получающий чтения строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер, содержащий обычные данные, полученные из [классе CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта. Независимо от типа данных буфера, переданного этому методу, он не выполняет любой манипуляций с данными (например, при преобразовании в Юникод), необходимо сопоставить возвращенные данные в структуру предполагается, что, как если бы **void\***  типа были возвращены.  
  
 **Значение NULL** был достигнут конец файла, не считывая все данные; или, если логический, **FALSE** если достигнут конец файла, не считывая все данные.  
  
### <a name="remarks"></a>Примечания  
 Функция помещает результирующий линию в память, ссылается `pstr` параметра. Останавливает, чтение знаков при достижении максимальное число символов, заданные `nMax`. Буфер всегда получает завершающий символ null.  
  
 При вызове метода `ReadString` без предварительного вызова функции [SetReadBufferSize](#setreadbuffersize), вы получите запас размером по 4 096 байт.  
  
##  <a name="seek"></a>CInternetFile::Seek  
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
 Относительная ссылка для смещения. Должен быть одним из следующих значений:  
  
- **CFile::begin** переместить указатель на файл `lOff` байтов вперед от начала файла.  
  
- **CFile::current** переместить указатель на файл `lOff` байтов из текущего положения в файле.  
  
- **CFile::end** переместить указатель на файл `lOff` байт в конце файла. `lOff`должно быть отрицательным для поиска в существующий файл. положительные значения будут поиска после конца файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый байт смещение от начала файла запрошенной позиции допустим; в противном случае — значение не определено и [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта создается исключение.  
  
### <a name="remarks"></a>Примечания  
 `Seek` Функция позволяет произвольный доступ к содержимому файла, перемещая указатель заданного значения имеет абсолютного или относительного. Нет данных фактически считывается в процессе поиска.  
  
 В данный момент вызов этой функции-члена поддерживается только для данных, связанных с `CHttpFile` объектов. Не поддерживается для запросов FTP или gopher. При вызове метода `Seek` одной из этих служб не поддерживается, он будет передавать обратно коду ошибки Win32 **ERROR_INTERNET_INVALID_OPERATION**.  
  
 При открытии файла указатель файла — со смещением 0, в начало файла.  
  
> [!NOTE]
>  С помощью `Seek` может привести к неявный вызов [Flush](#flush).  
  
### <a name="example"></a>Пример  
  Далее приведен пример реализации базового класса ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 Вызовите эту функцию-член для размера временной чтения буфера, используемого `CInternetFile`-производного объекта.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nReadSize*  
 Требуемый размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Базовые интерфейсы API WinInet не выполняют буферизацию, выберите размер буфера, который позволяет приложению считывать данные эффективно, независимо от объема данных для чтения. Если при каждом вызове функции [чтения](#read) обычно включает в себя большое aount данных (например, четыре или более килобайт), нет необходимости буфера. Тем не менее при вызове метода **чтения** для получения небольших объемов данных, или если вы используете [ReadString](#readstring) для чтения отдельных строк одновременно, то буфера чтения позволяет повысить производительность приложений.  
  
 По умолчанию `CInternetFile` объект не имеет буферизации для чтения. Если вызвать эту функцию-член, необходимо убедиться, что файл был открыт для доступа на чтение.  
  
 Можно увеличить размер буфера в любое время, но сжатие буфер не будет действовать. При вызове метода [ReadString](#readstring) без предварительного вызова функции `SetReadBufferSize`, вы получите запас размером по 4 096 байт.  
  
##  <a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 Вызовите эту функцию-член для размера буфера временной записи, используемые `CInternetFile`-производного объекта.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nWriteSize*  
 Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Поэтому базовый API-интерфейсы WinInet не выполняют буферизацию, выбрать размер буфера, который позволяет приложению записывать данные эффективно независимо от объема данных, которые требуется записать. Если при каждом вызове функции [записи](#write) обычно включает в себя большие объемы данных (например, четыре или более килобайт одновременно), нет необходимости буфера. Тем не менее при вызове метода [записи](#write) в записи небольших объемов данных, буфер записи может улучшить производительность приложения.  
  
 По умолчанию `CInternetFile` объект не имеет буферизации для записи. Если вызвать эту функцию-член, необходимо убедиться, что файл был открыт для записи. Размер буфера записи можно изменить в любое время, но при этом неявный вызов [Flush](#flush).  
  
##  <a name="write"></a>CInternetFile::Write  
 Вызовите эту функцию-член для записи в областях памяти `lpvBuf`, заданное число байтов, `nCount`.  
  
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
  
##  <a name="writestring"></a>CInternetFile::WriteString  
 Эта функция записывает строку, завершающуюся значением null связанного файла.  
  
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
