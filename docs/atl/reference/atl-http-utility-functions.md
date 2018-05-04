---
title: Служебные функции ATL HTTP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 476ca29de5a44e8ebb20d53ec0b88834c7b03eea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-http-utility-functions"></a>Служебные функции HTTP ATL

Эти функции поддерживают обработку URL-адресов.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Канонизирует URL-адрес, который включает преобразование небезопасных символов и пробелов в escape-последовательности.|  
|[AtlCombineUrl](#atlcombineurl)|Базовый URL-адрес и относительный URL-адрес объединены в один канонический URL-адрес.|  
|[AtlEscapeUrl](#atlescapeurl)|Преобразует все небезопасные символы в escape-последовательности.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Возвращает номер порта по умолчанию, связанного с определенным Интернет-протоколом или схемой.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Определяет, является ли символ для использования в URL-АДРЕСЕ.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Преобразует escape-символы обратно к исходным значениям.|  
|[RGBToHtml](#rgbtohtml)|Преобразует [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение в HTML-текст, соответствующий этому значению цвета.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|

## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl
Вызывайте эту функцию для приведения URL-адреса к каноническому виду, что включает преобразование небезопасных символов и пробелов в escape-последовательности.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `szUrl`  
 URL-адрес для каноникализации.  
  
 `szCanonicalized`  
 Выделенный вызывающим объектом буфер для получения каноническому URL-адрес.  
  
 `pdwMaxLength`  
 Указатель на переменную, которая содержит длину в символах `szCanonicalized`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего символа null.  
  
 `dwFlags`  
 Флаги ATL_URL управление работы этой функции. 

- `ATL_URL_BROWSER_MODE` Не кодирование или декодирование символов после «#» или «?» и не удаляет пробелы после «?». Если это значение не задано, кодируется весь URL-адрес и удалить конечные пробелы.
- `ATL_URL_DECODE` Преобразует все % XX последовательности символов, включая escape-последовательностей, прежде чем разбор URL-адрес.
- `ATL_URL_ENCODE_PERCENT` Кодирует все символы процента обнаружил. По умолчанию не кодируются символы процента.
- `ATL_URL_ENCODE_SPACES_ONLY` Кодирует только пробелы.
- `ATL_URL_ESCAPE` Преобразует все escape-последовательности (% XX) их соответствующих символов.
- `ATL_URL_NO_ENCODE` Не выполняет преобразование небезопасных символов в escape-последовательности.
- `ATL_URL_NO_META` Не приводит к удалению meta последовательности (такие как «. «и»..») по URL-адресу. 
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Ведет себя как текущая версия [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) , но не требует WinInet или Internet Explorer, должны быть установлены.  
  
### <a name="see-also"></a>См. также  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="atlcombineurl"></a> AtlCombineUrl
 Вызывайте эту функцию для объединения базового и относительного URL-адресов в один канонический URL-адрес.  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *szBaseUrl*  
 Базовый URL-адрес.  
  
 *szRelativeUrl*  
 URL-адрес, относительно базового URL-адреса.  
  
 `szBuffer`  
 Выделенный вызывающим объектом буфер для получения каноническому URL-адрес.  
  
 `pdwMaxLength`  
 Указатель на переменную, которая содержит длину в символах `szBuffer`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего символа null.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. В разделе [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Ведет себя как текущая версия [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) , но не требует WinInet или Internet Explorer, должны быть установлены.  
  
## <a name="atlescapeurl"></a> AtlEscapeUrl
 Вызывайте эту функцию для преобразования всех небезопасных символов в escape-последовательности.  
  
```    
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
 `lpszStringIn`  
 URL-адрес для преобразования.  
  
 `lpszStringOut`  
 Выделенный вызывающим объектом буфер, в который будет записан преобразованный URL-адрес.  
  
 `pdwStrLen`  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, `pdwStrLen` Получает количество символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего символа null. При использовании этого метода версия расширенных символов `pdwStrLen` Получает число символов, не количество байтов.  
  
 `dwMaxLength`  
 Размер буфера `lpszStringOut`.  
  
 `dwFlags`  
 Флаги ATL_URL управление работы этой функции. В разделе [ATLCanonicalizeUrl](#atlcanonicalizeurl) возможные значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
## <a name="atlgetdefaulturlport"></a> 
 Вызывайте эту функцию для получения номера порта по умолчанию, связанного с определенным интернет-протоколом или схемой.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, идентифицирующее схемы, для которого требуется получить номер порта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) связанные с заданной схемой или ATL_URL_INVALID_PORT_NUMBER, если схема не распознан.  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Символ, который проверяется на безопасность.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если введенный символ является небезопасным, **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Символы, которые не должны использоваться в URL-адреса можно проверить с помощью этой функции и преобразовывать с помощью [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="atlunescapeurl"></a> AtlUnescapeUrl
 Вызывайте эту функцию для обратного преобразования escape-символов в первоначальные значения.  
  
```    
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
 `lpszStringIn`  
 URL-адрес для преобразования.  
  
 `lpszStringOut`  
 Выделенный вызывающим объектом буфер, в который будет записан преобразованный URL-адрес.  
  
 `pdwStrLen`  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий символ null. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего символа null.  
  
 `dwMaxLength`  
 Размер буфера `lpszStringOut`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Обращает процесс преобразования, применяемая с [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a> RGBToHtml
Преобразует [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение в HTML-текст, соответствующий этому значению цвета.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Значение цвета RGB.  
  
 `pbOut`  
 Выделенный вызывающим объектом буфер для получения текста для HTML-значение цвета. Буфер должен иметь места для по крайней мере 8 символов, включая пространство для завершающего нуль-символа).  
  
 *nBuffer*  
 Размер в байтах буфера (включая пространство для завершающего нуль-символа).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Значение цвета HTML является знак решетки, за которым следует шестнадцатеричное значение 6-значного, с помощью 2 цифры для каждого из компонентов красного, зеленого и синего цвета (например, #FFFFFF отображается белый цвет).  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Параметры  
 `st`  
 Системное время, чтобы получить строку в формате HTTP.  
  
 *strTime*  
 Ссылку на строковую переменную для получения HTTP согласно спецификации RFC 2616 Дата и время ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) и RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)   

