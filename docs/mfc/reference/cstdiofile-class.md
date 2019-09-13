---
title: Класс Кстдиофиле
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 4b667f4121d92863335befda3a7beef74f29ad1a
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177489"
---
# <a name="cstdiofile-class"></a>Класс Кстдиофиле

Представляет потоковый файл времени выполнения языка C, Открытый в функции времени выполнения [fopen](../../c-runtime-library/reference/fopen-wfopen.md).

## <a name="syntax"></a>Синтаксис

```
class CStdioFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кстдиофиле:: Кстдиофиле](#cstdiofile)|`CStdioFile` Конструирует объект на основе пути или указателя файла.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кстдиофиле:: Open](#open)|Перегружен. Метод Open предназначен для использования с конструктором `CStdioFile` по умолчанию (переопределяет [кфиле:: Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|Считывает одну строку текста.|
|[Кстдиофиле:: Seek](#seek)|Позиционирует текущий указатель на файл.|
|[CStdioFile::WriteString](#writestring)|Записывает одну строку текста.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Содержит указатель на открытый файл.|

## <a name="remarks"></a>Примечания

Потоковые файлы буферизованы и могут быть открыты в текстовом режиме (по умолчанию) или в двоичном режиме.

Текстовый режим обеспечивает специальную обработку для пар символов возврата каретки и перевода строки. При записи символа перевода строки (0x0A) в объект текстового режима `CStdioFile` в файл отправляется пара байтов (0x0D, 0x0A). При чтении пара байтов (0x0D, 0x0A) преобразуется в один байт 0x0A.

Функции [кфиле](../../mfc/reference/cfile-class.md) , [дублировать](../../mfc/reference/cfile-class.md#duplicate), [локкранже](../../mfc/reference/cfile-class.md#lockrange)и [унлоккранже](../../mfc/reference/cfile-class.md#unlockrange) , не поддерживаются для `CStdioFile`.

При вызове этих функций в `CStdioFile`вы получите [кнотсуппортедексцептион](../../mfc/reference/cnotsupportedexception-class.md).

Дополнительные сведения об `CStdioFile`использовании см. в статьях [файлы MFC](../../mfc/files-in-mfc.md) и [Обработка файлов](../../c-runtime-library/file-handling.md) в справочнике по *библиотеке времени выполнения*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кфиле](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cstdiofile"></a>Кстдиофиле:: Кстдиофиле

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

*попенстреам*<br/>
Указывает указатель файла, возвращенный при вызове функции [fopen](../../c-runtime-library/reference/fopen-wfopen.md)среды выполнения C.

*лпсзфиленаме*<br/>
Указывает строку, которая является путем к требуемому файлу. Путь может быть как относительным, так и абсолютным.

*нопенфлагс*<br/>
Задает параметры для создания файлов, совместного использования файлов и режимов доступа к файлам. Можно указать несколько параметров с помощью побитового оператора или **|** ().

Требуется один параметр режима доступа к файлу; другие режимы являются необязательными. Список параметров режима и другие флаги см. в разделе [кфиле:: кфиле](../../mfc/reference/cfile-class.md#cfile) . В MFC версии 3,0 и более поздних разрешены общие флаги.

*pTM*<br/>
Указатель на объект Катлтрансактионманажер.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию не присоединяет файл к `CStdioFile` объекту. При использовании этого конструктора необходимо использовать `CStdioFile::Open` метод, чтобы открыть файл и присоединить его `CStdioFile` к объекту.

Конструктор с одним параметром присоединяет Открытый файловый поток к `CStdioFile` объекту. Допустимые значения указателя включают стандартные указатели входного и выходного файлов, *stdin*, *stdout*или *stderr*.

Конструктор с двумя параметрами создает `CStdioFile` объект и открывает соответствующий файл с заданным путем.

Если передать значение NULL для *попенстреам* или *лпсзфиленаме*, `CInvalidArgException*`конструктор выдаст исключение.

Если файл не может быть открыт или создан, конструктор создает исключение `CFileException*`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>Кстдиофиле:: m_pStream

Элемент данных — это указатель на открытый файл, возвращаемый функцией `fopen`времени выполнения C. `m_pStream`

```
FILE* m_pStream;
```

### <a name="remarks"></a>Примечания

Имеет значение NULL, если файл никогда не открывался или был закрыт.

##  <a name="open"></a>Кстдиофиле:: Open

Перегружен. Open предназначен для использования с конструктором по `CStdioFile` умолчанию.

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

*лпсзфиленаме*<br/>
Строка, которая является путем к требуемому файлу. Путь может быть как относительным, так и абсолютным.

*нопенфлагс*<br/>
Общий доступ и режим доступа. Указывает действие, выполняемое при открытии файла. Параметры можно комбинировать с помощью оператора побитового или (&#124;). Требуется одно разрешение на доступ и один параметр общего ресурса; режимы Модекреате и Моденоинхерит являются необязательными.

*pError*<br/>
Указатель на существующий объект исключения файла, который получит состояние невыполненной операции.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

##  <a name="readstring"></a>  CStdioFile::ReadString

Считывает текстовые данные в буфер до предельного числа символов *nмакс.* -1 из файла, связанного с `CStdioFile` объектом.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Параметры

*лпсз*<br/>
Задает указатель на предоставляемый пользователем буфер, который будет принимать текстовую строку, завершающуюся нулем.

*Nмакс.*<br/>
Указывает максимальное число считываемых символов, но не подсчитывает завершающий нуль символ.

*rStr*<br/>
Ссылка на `CString` объект, который будет содержать строку при возврате функции.

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер, содержащий текстовые данные. Значение NULL, если конец файла был достигнут без считывания данных; или значение FALSE, если конец файла был достигнут без считывания каких-либо данных.

### <a name="remarks"></a>Примечания

Чтение остановлено первым символом новой строки. Если в этом случае было считано менее *nмакс.* символов, то в буфере сохраняется символ новой строки. В любом случае добавляется символ null ("\ 0").

[Кфиле:: Read](../../mfc/reference/cfile-class.md#read) также доступен для ввода в текстовом режиме, но не заканчивается на паре символов возврата каретки и перевода строки.

> [!NOTE]
>  Версия этой функции удаляет при наличии значение `'\n'` , а версия LPTSTR — нет. `CString`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>Кстдиофиле:: Seek

Перемещает указатель в ранее открытый файл.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Параметры

*лофф*<br/>
Число байтов для перемещения указателя.

*Nиз*<br/>
Режим перемещения указателя. Должно иметь одно из следующих значений:

- `CFile::begin`: Переместите указатель файла *ЛОФФ* байт вперед от начала файла.

- `CFile::current`: Переместите указатель файла *ЛОФФ* байт из текущей позиции в файле.

- `CFile::end`: Переместите указатель файла *ЛОФФ* байт из конца файла. Обратите внимание, что *ЛОФФ* должен быть отрицательным для поиска в существующем файле. положительные значения будут искать после конца файла.

### <a name="return-value"></a>Возвращаемое значение

Если запрошенная позиция является допустимой `Seek` , возвращает новое смещение в байтах от начала файла. В противном случае возвращаемое значение не определено и `CFileException` создается объект.

### <a name="remarks"></a>Примечания

`Seek` Функция позволяет получить произвольный доступ к содержимому файла, перемещая указатель на указанную величину, абсолютно или относительно. Во время поиска данные в действительности не считываются. Если запрошенная длина превышает размер файла, то размер файла будет расширен до этой длины, и исключение не будет создано.

При открытии файла указатель файла позиционируется по смещению 0, началу файла.

Эта реализация `Seek` основана на функции `fseek`библиотеки времени выполнения (CRT). Существует несколько ограничений на использование `Seek` в потоках, открытых в текстовом режиме. Дополнительные сведения см. в разделе [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Пример

В следующем примере показано, как использовать `Seek` для перемещения указателя 1000 байт с начала `cfile` файла. Обратите `Seek` внимание, что не считывает данные, поэтому для чтения данных необходимо впоследствии вызвать метод [кстдиофиле:: ReadString](#readstring) .

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>Кстдиофиле:: WriteString

Записывает данные из буфера в файл, связанный с `CStdioFile` объектом.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Параметры

*лпсз*<br/>
Указывает указатель на буфер, содержащий строку, завершающуюся нулем.

### <a name="remarks"></a>Примечания

Завершающий нуль-символ ( `\0`) не записывается в файл. Этот метод записывает символы новой строки в *лпсз* в файл в виде пары символов возврата каретки и перевода строки.

Если требуется записать данные, не заканчивающиеся символом NULL, в файл, используйте `CStdioFile::Write` или [кфиле:: Write](../../mfc/reference/cfile-class.md#write).

Этот метод создает исключение `CInvalidArgException*` , если для параметра *лпсз* указано значение null.

Этот метод вызывает исключение `CFileException*` в ответ на ошибки файловой системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>См. также

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Кфиле::D блировать](../../mfc/reference/cfile-class.md#duplicate)<br/>
[Кфиле:: Локкранже](../../mfc/reference/cfile-class.md#lockrange)<br/>
[Кфиле:: Унлоккранже](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)
