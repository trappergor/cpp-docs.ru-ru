---
title: Класс CInternetFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed85edeaf5400805d4628e10acab4cdf4af52082
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202734"
---
# <a name="cinternetfile-class"></a>Класс CInternetFile
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
|[CInternetFile::Flush](#flush)|Сбрасывает содержимое буфера записи и гарантирует, что данные в памяти записывается на целевой компьютер.|  
|[CInternetFile::GetLength](#getlength)|Возвращает размер файла.|  
|[CInternetFile::Read](#read)|Считывает число указанные байты.|  
|[CInternetFile::ReadString](#readstring)|Считывает поток символов.|  
|[CInternetFile::Seek](#seek)|Перемещает указатель в открытом файле.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Задает размер буфера, в которой будут считываться данные.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Задает размер буфера, в которую будут записаны данные.|  
|[CInternetFile::Write](#write)|Записывает число указанные байты.|  
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
 Предоставляет базовый класс для [CHttpFile](../../mfc/reference/chttpfile-class.md) и [CGopherFile](../../mfc/reference/cgopherfile-class.md) файл классов. Никогда не создаст `CInternetFile` объекта напрямую. Вместо этого создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете создать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 `CInternetFile` Функции-члены `Open`, `LockRange`, `UnlockRange`, и `Duplicate` не реализованы для `CInternetFile`. При вызове этих функций для `CInternetFile` объекта, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CInternetFile` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="abort"></a>  CInternetFile::Abort  
 Закрывает файл, связанный с данным объектом и он становится недоступным для чтения или записи.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.  
  
 При обработке исключений, `Abort` отличается от [закрыть](#close) два важных отличия. Во-первых, `Abort` функция не вызывает исключение в случае сбоев, так как он игнорирует сбоев. Во-вторых, `Abort` не **ASSERT** Если файл не был открыт или закрыт ранее.  
  
##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile  
 Эта функция-член вызывается, когда `CInternetFile` создается объект.  
  
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
 *hFile*  
 Дескриптор файла Интернета.  
  
 *pstrFileName*  
 Указатель на строку, содержащую имя файла.  
  
 *pConnection*  
 Указатель на [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) объекта.  
  
 *bReadMode*  
 Указывает, является ли файл только для чтения.  
  
 *hSession*  
 Дескриптор для Интернет-сеанс.  
  
 *pstrServer*  
 Указатель на строку, содержащую имя сервера.  
  
 *dwContext*  
 Идентификатор контекста для `CInternetFile` объекта. См. в разделе [основные сведения о WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создаст `CInternetFile` объекта напрямую. Вместо этого создайте объект одного из его производных классов, вызвав [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Вы также можете создать `CInternetFile` путем вызова метода [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>  CInternetFile::Close  
 Закрывает `CInternetFile` и освобождает его ресурсы.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл был открыт для записи, имеется неявный вызов [Flush](#flush) гарантировать, что все буферизованные данные записываются на узел. Следует вызывать `Close` когда вы закончите, с помощью файла.  
  
##  <a name="flush"></a>  CInternetFile::Flush  
 Вызовите эту функцию-член для записи содержимого буфера записи.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `Flush` чтобы гарантировать, что все данные в памяти фактически были записаны на целевой компьютер и гарантировать завершения транзакции с хост-компьютере. `Flush` действует только на `CInternetFile` открытых объектов для записи.  
  
##  <a name="getlength"></a>  CInternetFile::GetLength  
 Возвращает размер файла.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>  CInternetFile::m_hFile  
 Дескриптор файла, связанного с данным объектом.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET  
 Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернет.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>  CInternetFile::Read  
 Эта функция-член для чтения в областях памяти, начиная с вызова *lpvBuf*, указанное число байтов, *nCount*.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 */ / lpBuf*  
 Указатель на адрес в памяти, по которому считываются данные из файла.  
  
 *nCount*  
 Число записываемых байтов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество байтов, переданных в буфер. Возвращаемое значение может быть меньше, чем *nCount* если достигнут конец файла.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает число фактически считанных байтов — число, которое может быть меньше, чем *nCount* Если файл закончился. Если произошла ошибка при чтении файла, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) , описывающий ошибку. Обратите внимание, что чтение после завершения файла не является ошибкой и не может быть причиной выдачи исключения.  
  
 Чтобы гарантировать получение всех данных, приложение должно продолжить вызывать `CInternetFile::Read` пока этот метод возвращает ноль.  
  
##  <a name="readstring"></a>  CInternetFile::ReadString  
 Вызовите эта функция-член для чтения поток символов, пока не найдет символ новой строки.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *pstr*  
 Указатель на строку, которая получит строке выполняется чтение.  
  
 *Nмакс.*  
 Максимальное количество символов для чтения.  
  
 *rString*  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, получающий чтения строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер, содержащий простых данных, полученных из [CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта. Независимо от типа данных буфера, переданного этому методу, он не выполняет все манипуляции с данными (например, преобразование в Юникод), поэтому необходимо сопоставить возвращенные данные в структуру ожидается, что, как если бы **void** <strong>\*</strong> типа были возвращены.  
  
 Значение NULL, если был достигнут конец файла, не считывая все данные; или, если логический, значение FALSE, если конец файла был достигнут не считывая все данные.  
  
### <a name="remarks"></a>Примечания  
 Функция помещает результирующий линию в память, ссылается *pstr* параметра. Он прекращает чтение символов при переходе в максимальное количество символов, определяемое *Nмакс*. Буфер всегда получает завершающий нуль-символ.  
  
 При вызове метода `ReadString` без предварительного вызова функции [SetReadBufferSize](#setreadbuffersize), вы получите буфера 4096 байт.  
  
##  <a name="seek"></a>  CInternetFile::Seek  
 Вызовите эту функцию-член можно переместить указатель в уже открытого файла.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Параметры  
 *lOffset*  
 Смещение в байтах для перемещения указателя чтения и записи в файле.  
  
 *nFrom*  
 Относительная ссылка для смещения. Должен принимать одно из следующих значений:  
  
- `CFile::begin` Переместите указатель файла *lOff* байтов вперед от начала файла.  
  
- `CFile::current` Переместите указатель файла *lOff* байтов из текущей позиции в файле.  
  
- `CFile::end` Переместите указатель файла *lOff* байтах от конца файла. *lOff* должен быть отрицательное значение для поиска в существующий файл; положительные значения вызовет переход за пределами файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый байт смещение от начала файла, если запрошенной позиции является допустимым; в противном случае — значение не определено и [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта создается исключение.  
  
### <a name="remarks"></a>Примечания  
 `Seek` Функция позволяет произвольного доступа для содержимого файла, перемещая указатель указанного значения, имеет абсолютного или относительного. Нет данных фактически считанных во время поиска.  
  
 В настоящее время вызова эта функция-член поддерживается только для данных, связанных с `CHttpFile` объектов. Не поддерживается для запросов FTP или gopher. Если вы вызываете `Seek` для одного из этих служб не поддерживается, он будет передавать обратно коду ошибки Win32 ERROR_INTERNET_INVALID_OPERATION.  
  
 При открытии файла, указатель файла является по смещению 0, в начале файла.  
  
> [!NOTE]
>  С помощью `Seek` может привести к неявный вызов [Flush](#flush).  
  
### <a name="example"></a>Пример  
  См. пример для реализации базового класса ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize  
 Вызов для установки размера временного буфера чтения используется эта функция-член `CInternetFile`-объект, производный от.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nReadSize*  
 Требуемый размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Базовые интерфейсы API WinInet не выполняют буферизацию, поэтому выберите размер буфера, который позволяет приложению считывать данные эффективно, независимо от объема данных для чтения. Если при каждом вызове [чтения](#read) обычно включает в себя большой aount данных (например, четырьмя или большим числом килобайт), нет необходимости буфер. Тем не менее при вызове метода `Read` для получения небольших объемов данных, или если вы используете [ReadString](#readstring) для чтения отдельные строки одновременно, а затем буфера чтения позволяет повысить производительность приложений.  
  
 По умолчанию `CInternetFile` объект не поддерживает буферизации для чтения. Если вы вызываете эту функцию-член, необходимо убедиться, что файл был открыт для доступа на чтение.  
  
 Можно увеличить размер буфера в любое время, но сжатие буфера не окажет никакого воздействия. При вызове метода [ReadString](#readstring) без предварительного вызова функции `SetReadBufferSize`, вы получите буфера 4096 байт.  
  
##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize  
 Вызывайте эту функцию члена, чтобы задать размер буфера временной записи, используемые `CInternetFile`-объект, производный от.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Параметры  
 *nWriteSize*  
 Размер буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 В этом базовый API-интерфейсы WinInet не выполнить буферизацию, выберите размер буфера, который позволяет приложению записывать данные эффективно независимо от объема данных для записи. Если при каждом вызове [записи](#write) обычно включает в себя большой объем данных (например, четырьмя или большим числом килобайт за раз), нет необходимости буфер. Тем не менее при вызове метода [записи](#write) для записи небольших объемов данных, буфер записи улучшает производительность приложения.  
  
 По умолчанию `CInternetFile` объект не поддерживает буферизации для записи. Если вы вызываете эту функцию-член, необходимо убедиться, что файл был открыт для записи. Размер буфера записи можно изменить в любое время, но при этом неявный вызов [Flush](#flush).  
  
##  <a name="write"></a>  CInternetFile::Write  
 Вызов этой функции-члена для записи в областях памяти *lpvBuf*, указанное число байтов, *nCount*.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 */ / lpBuf*  
 Указатель на первый байт для записи.  
  
 *nCount*  
 Указывает число байтов для записи.  
  
### <a name="remarks"></a>Примечания  
 Если возникают ошибки при записи данных, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) объект, описывающий ошибку.  
  
##  <a name="writestring"></a>  CInternetFile::WriteString  
 Эта функция записывает строку, завершающуюся символом null к соответствующему файлу.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Параметры  
 *pstr*  
 Указатель на строку, содержащую содержимое для записи.  
  
### <a name="remarks"></a>Примечания  
 Если возникают ошибки при записи данных, функция создает [CInternetException](../../mfc/reference/cinternetexception-class.md) объект, описывающий ошибку.  
  
## <a name="see-also"></a>См. также  
 [Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)
