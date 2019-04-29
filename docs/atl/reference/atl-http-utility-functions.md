---
title: Служебные функции HTTP ATL
ms.date: 11/04/2016
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
ms.openlocfilehash: ed01253c579cb6bb529c65e65b7e5ce8686e0b27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260874"
---
# <a name="atl-http-utility-functions"></a>Служебные функции HTTP ATL

Эти функции поддерживают обработку URL-адреса.

|||
|-|-|
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Канонизирует URL-адрес, который включает преобразование небезопасных символов и пробелов в escape-последовательности.|
|[AtlCombineUrl](#atlcombineurl)|Объединяет базовый URL-адрес и относительный URL-адрес в один канонический URL-адрес.|
|[AtlEscapeUrl](#atlescapeurl)|Преобразует все небезопасные символы в escape-последовательности.|
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Получает номер порта по умолчанию, связанные с определенным Интернет-протоколом или схемой.|
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Определяет, является ли символ безопасным для использования в URL-адрес.|
|[AtlUnescapeUrl](#atlunescapeurl)|Преобразует escape-символы обратно к исходным значениям.|
|[RGBToHtml](#rgbtohtml)|Преобразует [COLORREF](/windows/desktop/gdi/colorref) значение HTML-текст, соответствующий этому значению цвета.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl

Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.

```cpp
inline BOOL AtlCanonicalizeUrl(
   LPCTSTR szUrl,
   LPTSTR szCanonicalized,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*szUrl*<br/>
URL-адрес для каноникализации.

*szCanonicalized*<br/>
Выделенный вызывающим объектом буфер для получения канонический URL-адрес.

*pdwMaxLength*<br/>
Указатель на переменную, которая содержит длину в символах *szCanonicalized*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.

*dwFlags*<br/>
ATL_URL флагов управления поведением этой функции.

- Не ATL_URL_BROWSER_MODE кодировать и декодировать знаки после «#» или «?» и не удаляет пробелы после «?». Если это значение не указано, кодируется весь URL-адрес и конечный пробел удаляется.

- ATL_URL_DECODE преобразует все % XX последовательности символов, включая escape-последовательности, прежде чем анализируется URL-адрес.

- Кодирует ATL_URL_ENCODE_PERCENT обнаружил любые знаки процента. По умолчанию символы процента не кодируются.

- Кодирует ATL_URL_ENCODE_SPACES_ONLY только пробелы.

- ATL_URL_ESCAPE преобразует все escape-последовательности (% XX) свои соответствующие символы.

- Не выполняет ATL_URL_NO_ENCODE преобразование небезопасных символов в escape-последовательности.

- ATL_URL_NO_META не удаляет meta последовательности (такие как «. «и»..») из URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Ведет себя как текущая версия [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla) , но не требует WinInet или Internet Explorer, должны быть установлены.

## <a name="atlcombineurl"></a> AtlCombineUrl

Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.

```cpp
inline BOOL AtlCombineUrl(
   LPCTSTR szBaseUrl,
   LPCTSTR szRelativeUrl,
   LPTSTR szBuffer,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*szBaseUrl*<br/>
Базовый URL-адрес.

*szRelativeUrl*<br/>
URL-адрес относительно базового URL-адреса.

*szBuffer*<br/>
Выделенный вызывающим объектом буфер для получения канонический URL-адрес.

*pdwMaxLength*<br/>
Указатель на переменную, которая содержит длину в символах *szBuffer*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.

*dwFlags*<br/>
Флаги, управляющие поведением этой функции. См. в разделе [AtlCanonicalizeUrl](#atlcanonicalizeurl).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Ведет себя как текущая версия [InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) , но не требует WinInet или Internet Explorer, должны быть установлены.

## <a name="atlescapeurl"></a> AtlEscapeUrl

Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.

```cpp
inline BOOL AtlEscapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();

inline BOOL AtlEscapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*lpszStringIn*<br/>
URL-адрес для преобразования.

*lpszStringOut*<br/>
Выделенный вызывающим объектом буфер, в который будет сохраняться преобразованный URL-адрес.

*pdwStrLen*<br/>
Указатель на переменную типа DWORD. Если функция выполняется успешно, *pdwStrLen* Получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа. При использовании этого метода версии расширенных символов *pdwStrLen* Получает число символов, не число байтов.

*dwMaxLength*<br/>
Размер буфера *lpszStringOut*.

*dwFlags*<br/>
ATL_URL флагов управления поведением этой функции. См. в разделе [ATLCanonicalizeUrl](#atlcanonicalizeurl) возможные значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort

Вызывайте эту функцию для получения номера порта по умолчанию, связанного с определенным интернет-протоколом или схемой.

```
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();
```

### <a name="parameters"></a>Параметры

*m_nScheme*<br/>
[ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, определяющий схему, для которого требуется получить номер порта.

### <a name="return-value"></a>Возвращаемое значение

[ATL_URL_PORT](atl-typedefs.md#atl_url_port) связанные с заданной схемой или ATL_URL_INVALID_PORT_NUMBER, если схема не распознан.

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar

Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.

```
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();
```

### <a name="parameters"></a>Параметры

*Чэнь*<br/>
Символ, который требуется проверить безопасность.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если введенный символ unsafe, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Символы, которые не должны использоваться в URL-адресах, может быть проверен с использованием этой функции и преобразуются с помощью [AtlCanonicalizeUrl](#atlcanonicalizeurl).

## <a name="atlunescapeurl"></a> AtlUnescapeUrl

Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.

```cpp
inline BOOL AtlUnescapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();

inline BOOL AtlUnescapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();
```

### <a name="parameters"></a>Параметры

*lpszStringIn*<br/>
URL-адрес для преобразования.

*lpszStringOut*<br/>
Выделенный вызывающим объектом буфер, в который будет сохраняться преобразованный URL-адрес.

*pdwStrLen*<br/>
Указатель на переменную типа DWORD. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.

*dwMaxLength*<br/>
Размер буфера *lpszStringOut*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Обращает процесс преобразования, примененное [AtlEscapeUrl](#atlescapeurl).

## <a name="rgbtohtml"></a> RGBToHtml

Преобразует [COLORREF](/windows/desktop/gdi/colorref) значение HTML-текст, соответствующий этому значению цвета.

```cpp
bool inline RGBToHtml(
   COLORREF color,
   LPTSTR pbOut,
   long nBuffer);
```

### <a name="parameters"></a>Параметры

*color*<br/>
Значение цвета RGB.

*pbOut*<br/>
Выделенный вызывающим объектом буфер для получения текст для значения цвета HTML. Буфер должен иметь места для по крайней мере 8 символов, включая пространство для завершающего).

*nBuffer*<br/>
Размер в байтах буфера (включая пространство для завершающего).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Значение цвета HTML является знак решетки, за которыми следует шестнадцатеричное значение из 6 цифр, с помощью двух цифр для каждого из компонентов красного, зеленого и синего цвета (например, #FFFFFF белый).

## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate

Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.

```cpp
inline void SystemTimeToHttpDate(
   const SYSTEMTIME& st,
   CStringA& strTime);
```

### <a name="parameters"></a>Параметры

*ST*<br/>
Системное время должны быть получены в виде строки формата HTTP.

*strTime*<br/>
Ссылку на строковую переменную для получения HTTP Дата и время, как определено в RFC 2616 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) и RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).

## <a name="see-also"></a>См. также

[Основные понятия](../active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl-com-desktop-components.md)<br/>
[InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)
