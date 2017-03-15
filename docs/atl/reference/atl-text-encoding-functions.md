---
title: "Кодировка функции ATL текста | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
caps.latest.revision: 3
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: 86433bebe3fe84a027d7725525e028d80b67e358
ms.lasthandoff: 02/24/2017

---
# <a name="atl-text-encoding-functions"></a>Кодировка функции текста ATL
Эти функции поддерживают текст кодирования и декодирования.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|   
|[AtlGetVersion](#atlgetversion)|Эта функция вызывается для получения версии библиотеки ATL, который используется.  |  
|[AtlHexDecode](#atlhexdecode)|Декодирует строку данных, которая была закодирована как шестнадцатеричный текст, например предыдущим вызовом [AtlHexEncode](#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.|
|[AtlHexEncode](#atlhexencode)|Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[AtlHexValue](#atlhexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Вызывайте эту функцию для преобразования строки Юникода в UTF-8. |
|[BEncode](#bencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B".|
|[BEncodeGetRequiredLength](#beencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[EscapeXML](#escapexml)|Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты.|
|[GetExtendedChars](#getextendedchars)|Вызывайте эту функцию для получения количества символов национального алфавита в строке.|
|[IsExtendedChar](#isextendedchar)|Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).|
|[QEncode](#qencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q".  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[QPDecode](#qpdecode)|Декодирует строку данных, которая была закодирована в кавычках печатные формате, например предыдущим вызовом [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).|
|[QPEncode](#qpencode)|Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[UUDecode](#uudecode)|Декодирует строку данных, которая была кодировке UUENCODE, например предыдущим вызовом [UUEncode](#uuencode).|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.|
|[UUEncode](#uuencode)|Вызывайте эту функцию для кодирования данных в кодировке UUEncode. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|

## <a name="requirements"></a>Требования  
 **Заголовок:** файла atlenc.h  
 
## <a name="a-nameatlgethexvaluea-atlgethexvalue"></a><a name="atlgethexvalue"></a>AtlGetHexValue
Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Шестнадцатеричный символ "0"-"9", «A»-«F» или от «»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретируется как шестнадцатеричное значение. Например входных данных "0" возвращает значение 0 и входным «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
## <a name="a-nameatlgetversiona-atlgetversion"></a><a name="atlgetversion"></a>AtlGetVersion
Эта функция вызывается для получения версии библиотеки ATL, который используется.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>Параметры  
 `pReserved`  
 Зарезервированные указатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `DWORD` версию библиотеки ATL, компилируются или выполняются в целочисленное значение.  
  
## <a name="example"></a>Пример  
 Функция должна вызываться следующим образом.  
  
 [!code-cpp[NVC_ATL_Utilities&#95;](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

## <a name="a-nameatlhexdecodea-atlhexdecode"></a><a name="atlhexdecode"></a>AtlHexDecode
Декодирует строку данных, которая была закодирована как шестнадцатеричный текст, например предыдущим вызовом [AtlHexEncode](#atlhexencode).  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `pSrcData`  
 Строка, содержащая данные для декодирования.  
  
 `nSrcLen`  
 Длина в символах `pSrcData`.  
  
 `pbDest`  
 Выделенный вызывающим объектом буфер для получения и расшифрованные данные.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в байтах `pbDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
## <a name="a-nameatlhexdecodegetrequiredlengtha-atlhexdecodegetrequiredlength"></a><a name="atlhexdecodegetrequiredlength"></a>AtlHexDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать расшифрованную строку из `nSrcLen` символов.  
  
## <a name="a-nameatlhexencodea-atlhexencode"></a><a name="atlhexencode"></a>AtlHexEncode
Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста.  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Буфер, содержащий данные для кодирования.  
  
 `nSrcLen`  
 Длина в байтах данных для кодирования.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных с кодировкой.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в символах, буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Каждый байт исходные данные кодируются как 2 шестнадцатеричных символов.  
  
## <a name="a-nameatlhexencodegetrequiredlengtha-atlhexencodegetrequiredlength"></a><a name="atlhexencodegetrequiredlength"></a>AtlHexEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, подлежащего кодированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
## <a name="a-nameatlhexvaluea-atlhexvalue"></a><a name="atlhexvalue"></a>AtlHexValue
Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Шестнадцатеричный символ "0"-"9", «A»-«F» или от «»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретируется как шестнадцатеричное значение. Например входных данных "0" возвращает значение 0 и входным «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
## <a name="a-nameatlunicodetoutf8a-atlunicodetoutf8"></a><a name="atlunicodetoutf8"></a>AtlUnicodeToUTF8
Вызывайте эту функцию для преобразования строки Юникода в UTF-8.  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *wszSrc*  
 Чтобы преобразовать строку в кодировке Юникод  
  
 `nSrc`  
 Длина в символах строки Юникода.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения преобразованной строки.  
  
 `nDest`  
 Длина буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество символов для преобразованной строки.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить размер буфера, необходимый для преобразованной строки, эта функция передача значения 0 `szDest` и `nDest`.  
  
## <a name="a-namebencodea-bencode"></a><a name="bencode"></a>BEncode  
Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B".  
  
```  
inline BOOL BEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Буфер, содержащий данные для кодирования.  
  
 `nSrcLen`  
 Длина в байтах данных для кодирования.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных с кодировкой.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в символах, буфера.  
  
 `pszCharSet`  
 Символ, который используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования «B» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-namebeencodegetrequiredlengtha-bencodegetrequiredlength"></a><a name="beencodegetrequiredlength"></a>BEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, подлежащего кодированию.  
  
 `nCharsetLen`  
 Длина в символах используется для преобразования символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования «B» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameescapexmla-escapexml"></a><a name="escapexml"></a>EscapeXML
Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты.  
  
```  
inline int EscapeXML(  
   const wchar_t * szIn,  
   int nSrcLen,  
   wchar_t * szEsc,  
   int nDestLen,  
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `szIn`  
 Строка для преобразования.  
  
 *nSrclen*  
 Длина в символах для преобразования строки.  
  
 *szEsc*  
 Выделенный вызывающим объектом буфер для получения преобразованной строки.  
  
 *nDestLen*  
 Длина в символах, буфера, выделенный вызывающим объектом.  
  
 `dwFlags`  
 Флаги, описывающие, как преобразование будет выполняться. В разделе [флаги ATL_ESC](http://msdn.microsoft.com/library/daf3aa3c-7498-4d63-9fb6-e05b4815c2b8).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина в символах Преобразованная строка.  
  
### <a name="remarks"></a>Примечания  
 В таблице показаны возможные преобразования, выполняемые этой функции:  
  
|Исходный код|Назначение|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="a-namegetextendedcharsa-getextendedchars"></a><a name="getextendedchars"></a>GetExtendedChars
Вызывайте эту функцию для получения количества символов национального алфавита в строке.  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `szSrc`  
 Строка для анализа.  
  
 `nSrcLen`  
 Длина строки в символах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество расширенных символов, найденных в строке определяется [IsExtendedChar](#isextendedchar).  
  
## <a name="a-nameisextendedchara-isextendedchar"></a><a name="isextendedchar"></a>IsExtendedChar
Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *CH*  
 Символ для тестирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если символ был расширен, **FALSE** в противном случае.  
  
## <a name="a-nameqencodea-qencode"></a><a name="qencode"></a>QEncode
Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q".  
  
```  
inline BOOL QEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet,  
   int* pnNumEncoded = NULL) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Буфер, содержащий данные для кодирования.  
  
 `nSrcLen`  
 Длина в байтах данных для кодирования.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных с кодировкой.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в символах, буфера.  
  
 `pszCharSet`  
 Символ, который используется для преобразования.  
  
 *pnNumEncoded*  
 Указатель на переменную, которая при возвращении содержит количество небезопасных знаков, которые должны были быть преобразованы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «Q» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqencodegetrequiredlengtha-qencodegetrequiredlength"></a><a name="qencodegetrequiredlength"></a>QEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, подлежащего кодированию.  
  
 `nCharsetLen`  
 Длина в символах используется для преобразования символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «Q» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqpdecodea-qpdecode"></a><a name="qpdecode"></a>QPDecode
Декодирует строку данных, которая была закодирована в кавычках печатные формате, например предыдущим вызовом [QPEncode](#qpencode).  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pbSrcData`  
 Буфер, содержащий данные для декодирования.  
  
 [in] `nSrcLen`  
 Длина в байтах `pbSrcData`.  
  
 [выходной] `szDest`  
 Выделенный вызывающим объектом буфер для получения и расшифрованные данные.  
  
 [выходной] `pnDestLen`  
 Указатель на переменную, которая содержит длину в байтах `szDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера.  
  
 [in] `dwFlags`  
 Флаги, описывающие, как преобразование будет выполняться. В разделе [флаги ATLSMTP_QPENCODE](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения `FALSE` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Кавычки печатные кодировки описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpdecodegetrequiredlengtha-qpdecodegetrequiredlength"></a><a name="qpdecodegetrequiredlength"></a>QPDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать расшифрованную строку из `nSrcLen` символов.  
  
### <a name="remarks"></a>Примечания  
 Кавычки печатные кодировки описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodea-qpencode"></a><a name="qpencode"></a>QPEncode
Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).  
  
```  
inline BOOL QPEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Буфер, содержащий данные для кодирования.  
  
 `nSrcLen`  
 Длина в байтах данных для кодирования.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных с кодировкой.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в символах, буфера.  
  
 `dwFlags`  
 Флаги, описывающие, как преобразование будет выполняться. В разделе [флаги ATLSMTP_QPENCODE](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Кавычки печатные кодировки описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodegetrequiredlengtha-qpencodegetrequiredlength"></a><a name="qpencodegetrequiredlength"></a>QPEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, подлежащего кодированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Кавычки печатные кодировки описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameuudecodea-uudecode"></a><a name="uudecode"></a>UUDecode
Декодирует строку данных, которая была кодировке UUENCODE, например предыдущим вызовом [UUEncode](#uuencode).  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Строка, содержащая данные для декодирования.  
  
 `nSrcLen`  
 Длина в байтах `pbSrcData`.  
  
 `pbDest`  
 Выделенный вызывающим объектом буфер для получения и расшифрованные данные.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в байтах `pbDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации P1003.2b и D11 POSIX.  
  
## <a name="a-nameuudecodegetrequiredlengtha-uudecodegetrequiredlength"></a><a name="uudecodegetrequiredlength"></a>UUDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать расшифрованную строку из `nSrcLen` символов.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации P1003.2b и D11 POSIX.  
  
## <a name="a-nameuuencodea-uuencode"></a><a name="uuencode"></a>UUEncode
Вызывайте эту функцию для кодирования данных в кодировке UUEncode.  
  
```  
inline BOOL UUEncode(  
   const BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCTSTR lpszFile = _T("file"),  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `pbSrcData`  
 Буфер, содержащий данные для кодирования.  
  
 `nSrcLen`  
 Длина в байтах данных для кодирования.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных с кодировкой.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает необходимую длину в символах, буфера.  
  
 *lpszFile*  
 Файл добавляется к заголовку при ATLSMTP_UUENCODE_HEADER в `dwFlags`.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. В разделе [флаги ATLSMTP_UUENCODE](http://msdn.microsoft.com/library/ecb79b81-b764-4a48-a05c-a9dee6e7bbce).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации P1003.2b и D11 POSIX.  
  
## <a name="a-nameuuencodegetrequiredlengtha-uuencodegetrequiredlength"></a><a name="uuencodegetrequiredlength"></a>UUEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, подлежащего кодированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации P1003.2b и D11 POSIX.  
  
### <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)   
