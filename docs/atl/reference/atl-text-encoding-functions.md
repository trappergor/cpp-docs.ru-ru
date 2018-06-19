---
title: Кодировка функции ATL текста | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
ms.openlocfilehash: 26eb0709c4009070e6255c6ee178f19d13d8a9c3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366082"
---
# <a name="atl-text-encoding-functions"></a>Кодировка функции ATL текста
Эти функции поддерживают текст кодирования и декодирования.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|   
|[AtlGetVersion](#atlgetversion)|Вызывайте эту функцию, чтобы получить версию библиотеки ATL, вы используете.  |  
|[AtlHexDecode](#atlhexdecode)|Декодирует строку данных, которая была закодирована как шестнадцатеричный текст, например предыдущим вызовом [AtlHexEncode](#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.|
|[AtlHexEncode](#atlhexencode)|Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[AtlHexValue](#atlhexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Вызывайте эту функцию для преобразования строки Юникода в UTF-8. |
|[BEncode](#bencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B".|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[EscapeXML](#escapexml)|Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты.|
|[GetExtendedChars](#getextendedchars)|Вызывайте эту функцию для получения количества символов национального алфавита в строке.|
|[IsExtendedChar](#isextendedchar)|Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).|
|[QEncode](#qencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q".  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[QPDecode](#qpdecode)|Декодирует строку данных, которая была закодирована в quoted-printable формате, например предыдущим вызовом [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).|
|[QPEncode](#qpencode)|Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[UUDecode](#uudecode)|Декодирует строку данных, которая была закодирована в кодировке UUENCODE например предыдущим вызовом [UUEncode](#uuencode).|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.|
|[UUEncode](#uuencode)|Вызывайте эту функцию для кодирования данных в кодировке UUEncode. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|

## <a name="requirements"></a>Требования  
 **Заголовок:** файла atlenc.h  
 
## <a name="atlgethexvalue"></a> AtlGetHexValue
Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Шестнадцатеричный символ "0"-"9", «A»-«F» или от «»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретируется как шестнадцатеричная цифра. Например входных данных "0" возвращает значение 0 и входным «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
## <a name="atlgetversion"></a> AtlGetVersion
Вызывайте эту функцию, чтобы получить версию библиотеки ATL, вы используете.  
  
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
  
 [!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

## <a name="atlhexdecode"></a> AtlHexDecode
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
 Указатель на переменную, которая содержит длину в байтах `pbDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированную строку из `nSrcLen` символов.  
  
## <a name="atlhexencode"></a> AtlHexEncode
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
 Длина в байтах для кодирования данных.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Каждый байт исходные данные кодируются как 2 шестнадцатеричных символов.  
  
## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
## <a name="atlhexvalue"></a> AtlHexValue
Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `chIn`  
 Шестнадцатеричный символ "0"-"9", «A»-«F» или от «»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретируется как шестнадцатеричная цифра. Например входных данных "0" возвращает значение 0 и входным «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
## <a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8
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
 Длина в символах строку в кодировке Юникод.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения преобразованной строки.  
  
 `nDest`  
 Длина буфера в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число символов в преобразованную строку.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить размер буфера, необходимый для преобразованной строки, вызовите эту функцию, значение 0 `szDest` и `nDest`.  
  
## <a name="bencode"></a> BEncode  
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
 Длина в байтах для кодирования данных.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 `pszCharSet`  
 Символ, который используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2047 схеме кодировки «B» ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, для кодирования.  
  
 `nCharsetLen`  
 Длина в символах символа, который используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2047 схеме кодировки «B» ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="escapexml"></a> EscapeXML
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
 ATL_ESC флаги, описывающие, как преобразование не будет выполняться. 

- `ATL_ESC_FLAG_NONE` Поведение по умолчанию. Квота метки и апострофы не преобразуются.
- `ATL_ESC_FLAG_ATTR` Квота метки и апострофы преобразуются в `&quot;` и `&apos;` соответственно.


  
### <a name="return-value"></a>Возвращаемое значение  
 Длина в символах преобразованную строку.  
  
### <a name="remarks"></a>Примечания  
 В таблице показаны возможные преобразования, выполняемые этой функции:  
  
|Исходный код|Назначение|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="getextendedchars"></a> GetExtendedChars
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
 Возвращает количество расширенных символов, найдено в строке определяется [IsExtendedChar](#isextendedchar).  
  
## <a name="isextendedchar"></a> IsExtendedChar
Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *ch*  
 Символ, который необходимо протестировать  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если расширенный символ, **FALSE** в противном случае.  
  
## <a name="qencode"></a> QEncode
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
 Длина в байтах для кодирования данных.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 `pszCharSet`  
 Символ, который используется для преобразования.  
  
 *pnNumEncoded*  
 Указатель на переменную, которая при возвращении содержит количество небезопасных символов, которые должны были быть преобразован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2047 схеме кодировки «Q» ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, для кодирования.  
  
 `nCharsetLen`  
 Длина в символах символа, который используется для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2047 схеме кодировки «Q» ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qpdecode"></a> QPDecode
Декодирует строку данных, которая была закодирована в quoted-printable формате, например предыдущим вызовом [QPEncode](#qpencode).  
  
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
 Указатель на переменную, которая содержит длину в байтах `szDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
 [in] `dwFlags`  
 Флаги, описывающие, как преобразование не будет выполняться. В разделе [флаги ATLSMTP_QPENCODE](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения `FALSE` при сбое.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2045 quoted-printable схему кодирования ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированную строку из `nSrcLen` символов.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2045 quoted-printable схему кодирования ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencode"></a> QPEncode
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
 Длина в байтах для кодирования данных.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 `dwFlags`  
 ATLSMTP_QPENCODE флаги, описывающие, как преобразование не будет выполняться. 
- `ATLSMTP_QPENCODE_DOT` Если период появляется в начале строки, он добавлен к выходу обеспечении, кодировке.
- `ATLSMTP_QPENCODE_TRAILING_SOFT` Добавляет `=\r\n` закодированная строка.

Описывается в схеме кодировки quoted-printable [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt).
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2045 quoted-printable схему кодирования ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Описано в RFC 2045 quoted-printable схему кодирования ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="uudecode"></a> UUDecode
Декодирует строку данных, которая была закодирована в кодировке UUENCODE например предыдущим вызовом [UUEncode](#uuencode).  
  
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
 Указатель на переменную, которая содержит длину в байтах `pbDest`. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации POSIX P1003.2b/D11.  
  
## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированную строку из `nSrcLen` символов.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации POSIX P1003.2b/D11.  
  
## <a name="uuencode"></a> UUEncode
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
 Длина в байтах для кодирования данных.  
  
 `szDest`  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 `pnDestLen`  
 Указатель на переменную, которая содержит длину в символах `szDest`. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 *lpszFile*  
 Файл для добавления в заголовок ATLSMTP_UUENCODE_HEADER, заданные в `dwFlags`.  
  
 `dwFlags`  
 Флаги управления поведением этой функции. 
- `ATLSMTP_UUENCODE_HEADE` Заголовок будет закодировано.
- `ATLSMTP_UUENCODE_END` Конец кодируется.
- `ATLSMTP_UUENCODE_DOT` Запечатыванием данных будет выполняться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации POSIX P1003.2b/D11.  
  
## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 `nSrcLen`  
 Число байтов данных, для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество символов, необходимых для буфера, который может содержать закодированные данные `nSrcLen` байт.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соответствует спецификации POSIX P1003.2b/D11.  
  
### <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)   