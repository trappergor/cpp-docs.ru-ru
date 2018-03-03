---
title: "Класс CStdioFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 868442a2936781ed24588f47dcb591cadcc48f0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cstdiofile-class"></a>Класс CStdioFile
Представляет файл потока среды выполнения C, как открытые с помощью функции времени выполнения [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|Создает `CStdioFile` объекта из пути или файловом указателя.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|Перегружен. Открыть предназначен для использования со значением по умолчанию `CStdioFile` конструктор (переопределяет [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|Считывает одну строку текста.|  
|[CStdioFile::Seek](#seek)|Помещает текущего указателя файла.|  
|[CStdioFile::WriteString](#writestring)|Записывает одну строку текста.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|Содержит указатель на открытый файл.|  
  
## <a name="remarks"></a>Примечания  
 Поток файлы помещаются в буфер и можно открыть в текстовом режиме (по умолчанию) или двоичном режиме.  
  
 Текстовый режим предоставляет специальной обработкой пар перевода строки возврата каретки. При создании новой строки символов в текстовом режиме (0x0A) `CStdioFile` объект, пару байтов (0x0D, 0x0A) отправляется в файл. При чтении, пара байтов (0x0D, 0x0A) преобразуются в один байт 0x0A.  
  
 [CFile](../../mfc/reference/cfile-class.md) функции [дублировать](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не поддерживается для `CStdioFile`.  
  
 При вызове этих функций для `CStdioFile`, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения об использовании `CStdioFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cstdiofile"></a>CStdioFile::CStdioFile  
 Создает и инициализирует объект `CStdioFile`.  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Параметры  
 `pOpenStream`  
 Указывает файл указатель, возвращенный вызовом функции времени выполнения C [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 `lpszFileName`  
 Задает строку, которая представляет путь к нужному файлу. Путь может быть относительным или абсолютным.  
  
 `nOpenFlags`  
 Задает параметры для создания файла, общий доступ к файлам и режима доступа к файлам. Можно указать несколько параметров с помощью побитового или ( `|`) оператор.  
  
 Требуется один параметр режим доступа file; другие режимы являются необязательными. В разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) список параметров режима и другие флаги. В MFC 3.0 и более поздних версий допускаются флаги общего ресурса.  
  
 `pTM`  
 Указатель на объект catltransactionmanager.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию не присоединяет файл к `CStdioFile` объекта. При использовании этого конструктора, необходимо использовать `CStdioFile::Open` метод, чтобы открыть файл и присоединить его к `CStdioFile` объекта.  
  
 Единственным параметром конструктора присоединяет поток открыть файл для `CStdioFile` объекта. Разрешены значения указателя включают указатели стандартных файлов ввода вывода `stdin`, `stdout`, или `stderr`.  
  
 Два параметра конструктор создает `CStdioFile` объекта и открывает соответствующий файл по указанному пути.  
  
 Если передать `NULL` либо `pOpenStream` или `lpszFileName`, конструктор вызывает `CInvalidArgException*`.  
  
 Если не удается открыть или создать файл, конструктор вызывает `CFileException*`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>CStdioFile::m_pStream  
 `m_pStream` Член данных — указатель на открытый файл, возвращенный функции времени выполнения C `fopen`.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>Примечания  
 Это **NULL** Если файл никогда не был открыт или закрыт.  
  
##  <a name="open"></a>CStdioFile::Open  
 Перегружен. Открыть предназначен для использования со значением по умолчанию `CStdioFile` конструктор.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CAtlTransactionManager* pTM,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным или абсолютным.  
  
 `nOpenFlags`  
 Для управления доступом и режимом доступа. Указывает действие, выполняемое при открытии файла. Параметры могут быть объединены с помощью побитового или (&#124;) оператор. Разрешения на доступ к одной и одной общей папки параметр являются обязательными; режимы modeCreate и modeNoInherit являются необязательными.  
  
 `pError`  
 Указатель на существующий объект исключения файл, который получит состояние сбоя операции.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="readstring"></a>CStdioFile::ReadString  
 Считывает текстовые данные в буфер, в пределах `nMax`значение -1, символы из файла, связанного с `CStdioFile` объекта.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 Задает указатель на пользовательские буфера, который будет принимать строку текста с завершающим нулем.  
  
 `nMax`  
 Указывает максимальное число символов для чтения, не считая завершающий нуль-символ.  
  
 `rString`  
 Ссылку на `CString` объект, который будет содержать строку, когда функция возвращает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер, содержащий текстовые данные. **Значение NULL** Если был достигнут конец файла, не считывая все данные; или логическое значение **FALSE** если достигнут конец файла, не считывая все данные.  
  
### <a name="remarks"></a>Примечания  
 Чтение остановлена по первому знаку новой строки. Если в этом случае меньше, чем `nMax`были считаны-1 символ, символ перевода строки, сохраненного в буфере. В любом случае добавляется символ null («\0»).  
  
 [CFile::Read](../../mfc/reference/cfile-class.md#read) также доступна для входных данных в текстовом режиме, но не прекращает на пару перевода строки возврата каретки.  
  
> [!NOTE]
>  `CString` Удаляет версия этой функции `'\n'` при его наличии; `LPTSTR` версии не должно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>CStdioFile::Seek  
 Перемещает указатель в уже открытого файла.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Параметры  
 `lOff`  
 Число байтов для перемещения указателя.  
  
 `nFrom`  
 Режим перемещения указателя. Должен быть одним из следующих значений:  
  
- `CFile::begin`: Переместить указатель на файл `lOff` байтов вперед от начала файла.  
  
- `CFile::current`: Переместить указатель на файл `lOff` байтов из текущего положения в файле.  
  
- `CFile::end`: Переместить указатель на файл `lOff` байт в конце файла. Обратите внимание, что `lOff` должны быть отрицательным для поиска в существующую файловой; положительные значения будут поиска после конца файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если допустим запрошенной позиции `Seek` возвращает новый смещение в байтах от начала файла. В противном случае возвращаемое значение не определено и `CFileException` объекта создается исключение.  
  
### <a name="remarks"></a>Примечания  
 `Seek` Функция позволяет произвольный доступ к содержимому файла, перемещая указатель заданного значения имеет абсолютного или относительного. Нет данных фактически считывается в процессе поиска. Если запрошенной позиции больше, чем размер файла, длину файла будет распространяться на этой позиции и будет создано исключение.  
  
 При открытии файла указатель файла помещается со смещением 0, в начало файла.  
  
 Эта реализация `Seek` основана на функции библиотеки времени выполнения (CRT) `fseek`. Существуют некоторые ограничения на использование `Seek` для потоков, открытых в текстовом режиме. Дополнительные сведения см. в разделе [fseek _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как использовать `Seek` для перемещения указателя 1000 байт от начала `cfile` файла. Обратите внимание, что `Seek` не считывает данные, поэтому необходимо вызвать впоследствии [CStdioFile::ReadString](#readstring) для чтения данных.  
  
 [!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>CStdioFile::WriteString  
 Записывает данные из буфера в файл, связанный с `CStdioFile` объекта.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Параметры  
 `lpsz`  
 Определяет указатель на буфер, содержащий строку, завершающуюся значением null.  
  
### <a name="remarks"></a>Примечания  
 Завершающий символ null ( `\0`) не записывается в файл. Этот метод записывает символы новой строки `lpsz` файл как пара возврата каретки.  
  
 Если вы хотите записывать данные, не является нулем в файл с помощью `CStdioFile::Write` или [CFile::Write](../../mfc/reference/cfile-class.md#write).  
  
 Этот метод создает исключение `CInvalidArgException*` при указании `NULL` для `lpsz` параметра.  
  
 Этот метод создает исключение `CFileException*` в ответ на системные ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile-класс](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)
