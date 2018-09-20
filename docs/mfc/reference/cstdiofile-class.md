---
title: Класс CStdioFile | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbe6d2bd5ea8d03a73fd7389da9eeb0e7ca32cdf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442426"
---
# <a name="cstdiofile-class"></a>Класс CStdioFile

Представляет файл потока среды выполнения C, как открытые с помощью функции времени выполнения [fopen](../../c-runtime-library/reference/fopen-wfopen.md).

## <a name="syntax"></a>Синтаксис

```
class CStdioFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Создает `CStdioFile` из указателя путь или файл.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::Open](#open)|Перегружен. Открыть предназначен для использования со значением по умолчанию `CStdioFile` конструктор (переопределяет [CFile::Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|Читает одну строку текста.|
|[CStdioFile::Seek](#seek)|Помещает текущий указатель файла.|
|[CStdioFile::WriteString](#writestring)|Выводит отдельную строку текста.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Содержит указатель на открытый файл.|

## <a name="remarks"></a>Примечания

Stream файлы помещаются в буфер и могут быть открыты в текстовом режиме (по умолчанию) или двоичном режиме.

Текстовый режим предоставляет специальной обработкой пар перевода строки возврата каретки. При написании новой строки символов в текстовом режиме (0x0A) `CStdioFile` object, пары байтов (0x0D, 0x0A) отправляется в файл. При чтении, пары байтов (0x0D, 0x0A) преобразуется в один байт 0x0A.

[CFile](../../mfc/reference/cfile-class.md) функции [дублировать](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не поддерживаются для `CStdioFile`.

При вызове этих функций для `CStdioFile`, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Дополнительные сведения об использовании `CStdioFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile

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

*pOpenStream*<br/>
Указывает файл указатель, возвращенный вызовом функции времени выполнения C [fopen](../../c-runtime-library/reference/fopen-wfopen.md).

*lpszFileName*<br/>
Задает строку, — это путь к требуемому файлу. Путь может быть относительным или абсолютным.

*nOpenFlags*<br/>
Указывает параметры для создания файла, общий доступ к файлам и режима доступа к файлам. Можно указать несколько параметров с помощью побитовой операции или ( **|** ) оператор.

Необходим один из вариантов режим доступа для файла; другие режимы являются необязательными. См. в разделе [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) список вариантов и других флагов. В MFC 3.0 и более поздних версий допускаются флаги общего ресурса.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию не присоединяет файл к `CStdioFile` объекта. При использовании этого конструктора, необходимо использовать `CStdioFile::Open` метод, чтобы открыть файл и присоединить его к `CStdioFile` объекта.

Конструктор одного параметра прикрепляет поток открыть файл для `CStdioFile` объекта. Допускается указатель значения включают указатели предопределенные ввода вывода файла *stdin*, *stdout*, или *stderr*.

Создает параметр два конструктора `CStdioFile` объекта и открывает соответствующий файл по указанному пути.

Если передается значение NULL для либо *pOpenStream* или *lpszFileName*, конструктор вызывает `CInvalidArgException*`.

Если не удается открыть или создать файл, конструктор создает `CFileException*`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>  CStdioFile::m_pStream

`m_pStream` Данные-член — это указатель на открытый файл, возвращенный функцией среды выполнения C `fopen`.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Примечания

Возвращается значение NULL, если файл не был открыт или закрыт.

##  <a name="open"></a>  CStdioFile::Open

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

*lpszFileName*<br/>
Строка, — это путь к требуемому файлу. Путь может быть относительным или абсолютным.

*nOpenFlags*<br/>
Совместное использование и режимом доступа. Указывает действие, выполняемое при открытии файла. Параметры могут быть объединены с помощью побитового или (&#124;) оператор. Разрешение на доступ один параметр одну общую папку требуются и; режимы modeCreate и modeNoInherit являются необязательными.

*pError*<br/>
Указатель на существующий объект исключения файлов, который получит состояние сбоя операции.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

##  <a name="readstring"></a>  CStdioFile::ReadString

Считывает текстовые данные в буфер, но не более *Nмакс.* символов -1, из файла, связанного с `CStdioFile` объекта.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Задает указатель на буфер, предоставленные пользователем, который будет принимать строку текста с завершающим нулем.

*Nмакс.*<br/>
Указывает максимальное количество символов для чтения, не считая завершающий нуль-символ.

*rString*<br/>
Ссылку на `CString` объект, который будет содержать строку, когда функция возвращает.

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер, содержащий текстовые данные. Значение NULL, если был достигнут конец файла, не считывая все данные; или, если логический, значение FALSE, если конец файла был достигнут не считывая все данные.

### <a name="remarks"></a>Примечания

Чтение останавливается с первого символа новой строки. Если в этом случае меньше, чем *Nмакс.* будут прочитаны-1 символ, символ новой строки хранятся в буфере. В любом случае добавляется символ null («\0»).

[CFile::Read](../../mfc/reference/cfile-class.md#read) также доступна для входных данных в текстовом режиме, но не завершает работу на пару перевода строки возврата каретки.

> [!NOTE]
>  `CString` Удаляет версия этой функции `'\n'` при его наличии; не поддерживает версии LPTSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>  CStdioFile::Seek

Перемещает указатель в уже открытого файла.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Параметры

*lOff*<br/>
Число байтов для перемещения указателя.

*nFrom*<br/>
Режим перемещения указателя. Должен принимать одно из следующих значений:

- `CFile::begin`: Переместить указатель файла *lOff* байтов вперед от начала файла.

- `CFile::current`: Переместить указатель файла *lOff* байтов из текущей позиции в файле.

- `CFile::end`: Переместить указатель файла *lOff* байтах от конца файла. Обратите внимание, что *lOff* должен быть отрицательное значение для поиска в существующий файл; положительные значения вызовет переход за пределами файла.

### <a name="return-value"></a>Возвращаемое значение

Если запрошенной позиции является допустимым, `Seek` возвращает новый смещение в байтах от начала файла. В противном случае возвращаемое значение не определено и `CFileException` объекта создается исключение.

### <a name="remarks"></a>Примечания

`Seek` Функция позволяет произвольного доступа для содержимого файла, перемещая указатель указанного значения, имеет абсолютного или относительного. Нет данных фактически считанных во время поиска. Если запрошенной позиции больше, чем размер файла, длина файла будут отображаться в этой позиции, и возникает исключение.

При открытии файла, указатель файла помещается по смещению 0, в начале файла.

Эта реализация `Seek` основана на функции библиотеки времени выполнения (CRT) `fseek`. Существуют некоторые ограничения на использование `Seek` с потоками, открытыми в текстовом режиме. Дополнительные сведения см. в разделе [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Пример

В следующем примере показано, как использовать `Seek` для перемещения указателя мыши на 1000 байт в начале `cfile` файл. Обратите внимание, что `Seek` не считывает данные, поэтому впоследствии необходимо вызвать [CStdioFile::ReadString](#readstring) для чтения данных.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>  CStdioFile::WriteString

Записывает данные из буфера к файлу, связанному с `CStdioFile` объекта.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Параметры

*lpsz*<br/>
Задает указатель на буфер, содержащий заканчивающуюся нулем строку.

### <a name="remarks"></a>Примечания

Завершающий нуль-символ ( `\0`) не записывается в файл. Этот метод записывает символы новой строки *lpsz* файл как пара возврата каретки.

Если вы хотите записывать данные, не заканчивается нулевым байтом в файл с помощью `CStdioFile::Write` или [CFile::Write](../../mfc/reference/cfile-class.md#write).

Этот метод вызывает исключение `CInvalidArgException*` Если указано значение NULL для *lpsz* параметра.

Этот метод вызывает исключение `CFileException*` в ответ на системные ошибки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>См. также

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)
