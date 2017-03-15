---
title: "Служебные функции ATL HTTP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: dd8b3a279148e2a5b72d96724c329e49cd5d3e5f
ms.lasthandoff: 02/24/2017

---
# <a name="atl-http-utility-functions"></a>Служебные функции HTTP ATL

Эти функции поддерживают обработку URL-адресов.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Канонизирует URL-адрес, который включает преобразование небезопасных символов и пробелов в escape-последовательности.|  
|[AtlCombineUrl](#atlcombineurl)|Объединяет базовый URL-адрес и относительный URL-адрес в один канонический URL-адрес.|  
|[AtlEscapeUrl](#atlescapeurl)|Преобразует все небезопасные символы в escape-последовательности.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Возвращает номер порта по умолчанию, связанного с определенным Интернет-протоколом или схемой.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Определяет, является ли символ безопасный для использования в URL-АДРЕСЕ.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Преобразует escape-символы обратно к исходным значениям.|  
|[RGBToHtml](#rgbtohtml)|Преобразует [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) HTML-текст, соответствующий этому значению цвета.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Вызывайте эту функцию для преобразования системного времени в строку в формате, пригодном для использования в заголовках HTTP.|

## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  

## <a name="a-nameatlcanonicalizeurla-atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl
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
 Указатель на переменную, которая содержит длину в символах `szCanonicalized`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, не включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая места для завершающего символа null.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. В разделе [флаги ATL_URL](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Ведет себя как текущая версия [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) , но не требует WinInet или Internet Explorer, должны быть установлены.  
  
### <a name="see-also"></a>См. также  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="a-nameatlcombineurla-atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl
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
  
 `szBuffer`  
 Выделенный вызывающим объектом буфер для получения каноническому URL-адрес.  
  
 `pdwMaxLength`  
 Указатель на переменную, которая содержит длину в символах `szBuffer`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, не включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая места для завершающего символа null.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. В разделе [флаги ATL_URL](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Ведет себя как текущая версия [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) , но не требует WinInet или Internet Explorer, должны быть установлены.  
  
## <a name="a-nameatlescapeurla-atlescapeurl"></a><a name="atlescapeurl"></a>AtlEscapeUrl
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
 Выделенный вызывающим объектом буфер, в который будут записываться преобразованного URL-адреса.  
  
 `pdwStrLen`  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, `pdwStrLen` Получает количество символов, записанных в буфер, не включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая места для завершающего символа null. При использовании версии расширенных символов, этот метод `pdwStrLen` Получает число знаков, не число байтов.  
  
 `dwMaxLength`  
 Размер буфера `lpszStringOut`.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. В разделе [флаги ATL_URL](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
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

## <a name="a-nameatlisunsafeurlchara-atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 Вызывайте эту функцию, чтобы определить, безопасно ли использовать символ в URL-адресе.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Символ, который проверяется на безопасность.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если входной символ является небезопасным, **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Символы, которые не должны использоваться в URL-адреса можно проверить с помощью этой функции и преобразовывать с помощью [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="a-nameatlunescapeurla-atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl
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
 Выделенный вызывающим объектом буфер, в который будут записываться преобразованного URL-адреса.  
  
 `pdwStrLen`  
 Указатель на переменную типа DWORD. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер, не включая завершающий символ null. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера, включая места для завершающего символа null.  
  
 `dwMaxLength`  
 Размер буфера `lpszStringOut`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Отменяет процесс преобразования, применяемые [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="a-namergbtohtmla-rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml
Преобразует [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) HTML-текст, соответствующий этому значению цвета.  
  
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
 Выделенный вызывающим объектом буфер для получения текста для значение цвета HTML. Буфер должен иметь место для менее 8 символов, включая места для завершающего символа null).  
  
 *nBuffer*  
 Размер в байтах буфера (включая места для завершающего символа null).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Значение цвета HTML является знак решетки, за которым следует шестнадцатеричное значение 6-значного, с помощью двух цифр для каждого из компонентов красного, зеленого и синего цвета (например, #FFFFFF белый).  
  
## <a name="a-namesystemtimetohttpdatea-systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
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
 Ссылку на строковую переменную для получения HTTP Дата и время, как определено в RFC 2616 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) и RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)   


