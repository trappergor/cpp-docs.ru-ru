---
title: Служебные функции HTTP ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 224f4d78aec432a27b2a0258d0d6b3d4a8f2174d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209512"
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
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *szUrl*  
 URL-адрес для каноникализации.  
  
 *szCanonicalized*  
 Выделенный вызывающим объектом буфер для получения канонический URL-адрес.  
  
 *pdwMaxLength*  
 Указатель на переменную, которая содержит длину в символах *szCanonicalized*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.  
  
 *dwFlags*  
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
  
### <a name="see-also"></a>См. также  
 [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)

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
 URL-адрес относительно базового URL-адреса.  
  
 *szBuffer*  
 Выделенный вызывающим объектом буфер для получения канонический URL-адрес.  
  
 *pdwMaxLength*  
 Указатель на переменную, которая содержит длину в символах *szBuffer*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.  
  
 *dwFlags*  
 Флаги, управляющие поведением этой функции. См. в разделе [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Ведет себя как текущая версия [InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) , но не требует WinInet или Internet Explorer, должны быть установлены.  
  
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
 *lpszStringIn*  
 URL-адрес для преобразования.  
  
 *lpszStringOut*  
 Выделенный вызывающим объектом буфер, в который будет сохраняться преобразованный URL-адрес.  
  
 *pdwStrLen*  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, *pdwStrLen* Получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа. При использовании этого метода версии расширенных символов *pdwStrLen* Получает число символов, не число байтов.  
  
 *dwMaxLength*  
 Размер буфера *lpszStringOut*.  
  
 *dwFlags*  
 ATL_URL флагов управления поведением этой функции. См. в разделе [ATLCanonicalizeUrl](#atlcanonicalizeurl) возможные значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort
 Вызывайте эту функцию для получения номера порта по умолчанию, связанного с определенным интернет-протоколом или схемой.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, определяющий схему, для которого требуется получить номер порта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) связанные с заданной схемой или ATL_URL_INVALID_PORT_NUMBER, если схема не распознан.  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *Чэнь*  
 Символ, который требуется проверить безопасность.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если введенный символ unsafe, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Символы, которые не должны использоваться в URL-адресах, может быть проверен с использованием этой функции и преобразуются с помощью [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
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
 *lpszStringIn*  
 URL-адрес для преобразования.  
  
 *lpszStringOut*  
 Выделенный вызывающим объектом буфер, в который будет сохраняться преобразованный URL-адрес.  
  
 *pdwStrLen*  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, включая завершающий нуль-символ. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера, включая пространство для завершающего нуль-символа.  
  
 *dwMaxLength*  
 Размер буфера *lpszStringOut*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Обращает процесс преобразования, примененное [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a> RGBToHtml
Преобразует [COLORREF](/windows/desktop/gdi/colorref) значение HTML-текст, соответствующий этому значению цвета.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 Значение цвета RGB.  
  
 *pbOut*  
 Выделенный вызывающим объектом буфер для получения текст для значения цвета HTML. Буфер должен иметь места для по крайней мере 8 символов, включая пространство для завершающего).  
  
 *nBuffer*  
 Размер в байтах буфера (включая пространство для завершающего).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Значение цвета HTML является знак решетки, за которыми следует шестнадцатеричное значение из 6 цифр, с помощью двух цифр для каждого из компонентов красного, зеленого и синего цвета (например, #FFFFFF белый).  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Параметры  
 *ST*  
 Системное время должны быть получены в виде строки формата HTTP.  
  
 *strTime*  
 Ссылку на строковую переменную для получения HTTP Дата и время, как определено в RFC 2616 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) и RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)   

