---
title: Функции кодировки текста ATL | Документация Майкрософт
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
ms.openlocfilehash: 35f9d91164eccc5fc65d60050957a494993a4f11
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885537"
---
# <a name="atl-text-encoding-functions"></a>Функции кодировки текста ATL
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
|[QPDecode](#qpdecode)|Декодирует строку данных, которая была закодирована в формате quoted-printable, например предыдущим вызовом [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).|
|[QPEncode](#qpencode)|Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[UUDecode](#uudecode)|Декодирует строку данных, которая была закодирована в кодировке UUENCODE например предыдущим вызовом к [UUEncode](#uuencode).|
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
 *Чэнь*  
 Шестнадцатеричный символ "0"-"9", «A» — «F» или «а»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретированное как шестнадцатеричная цифра. Например входных данных "0" возвращает значение 0 и входных данных из «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
## <a name="atlgetversion"></a> AtlGetVersion
Вызывайте эту функцию, чтобы получить версию библиотеки ATL, вы используете.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>Параметры  
 *Сохранен*  
 Зарезервированный указатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение DWORD целого версии библиотеки ATL, компилируются или выполняются.  
  
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
 *pSrcData*  
 Строка, содержащая данные для декодирования.  
  
 *nSrcLen*  
 Длина в символах *pSrcData*.  
  
 *pbDest*  
 Выделенный вызывающим объектом буфер для получения декодированные данные.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в байтах *pbDest*. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированная строка со *nSrcLen* символов.  
  
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
 *pbSrcData*  
 Буфер, содержащий данные для кодирования.  
  
 *nSrcLen*  
 Длина в байтах для кодирования данных.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в символах *szDest*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Каждый байт исходные данные кодируются как 2 шестнадцатеричные символы.  
  
## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число байтов данных для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, необходимых для буфера, который может содержать закодированные данные из *nSrcLen* байт.  
  
## <a name="atlhexvalue"></a> AtlHexValue
Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *Чэнь*  
 Шестнадцатеричный символ "0"-"9", «A» — «F» или «а»-«f».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение входного символа, интерпретированное как шестнадцатеричная цифра. Например входных данных "0" возвращает значение 0 и входных данных из «A» возвращает значение 10. Если входной символ не является шестнадцатеричной цифрой, эта функция возвращает -1.  
  
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
  
 *nSrc*  
 Длина в символах строки Юникода.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения преобразованной строки.  
  
 *nDest*  
 Длина в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество символов для преобразованной строки.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить размер буфера, требуемого для преобразованной строки, вызовите эту функцию, передача значения 0 *szDest* и *nDest*.  
  
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
 *pbSrcData*  
 Буфер, содержащий данные для кодирования.  
  
 *nSrcLen*  
 Длина в байтах для кодирования данных.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в символах *szDest*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 *pszCharSet*  
 Набор знаков, используемый для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «B» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число байтов данных для кодирования.  
  
 *nCharsetLen*  
 Длина в символах, используется для преобразования символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, необходимых для буфера, который может содержать закодированные данные из *nSrcLen* байт.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «B» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
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
 *szIn*  
 Строка для преобразования.  
  
 *nSrclen*  
 Длина в символах строка для преобразования.  
  
 *szEsc*  
 Выделенный вызывающим объектом буфер для получения преобразованной строки.  
  
 *nDestLen*  
 Длина в символах, буфера, выделенный вызывающим объектом.  
  
 *dwFlags*  
 ATL_ESC флаги, описывающие, каким образом будет осуществляться преобразование. 

- Поведение по умолчанию ATL_ESC_FLAG_NONE. Квота метки и апострофы не преобразуются.
- Квота ATL_ESC_FLAG_ATTR метки и апострофы преобразуются в `&quot;` и `&apos;` соответственно.


  
### <a name="return-value"></a>Возвращаемое значение  
 Длина в символах преобразованной строки.  
  
### <a name="remarks"></a>Примечания  
 В таблице показаны возможные преобразования, выполняемые этой функцией:  
  
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
 *szSrc*  
 Строка для анализа.  
  
 *nSrcLen*  
 Длина строки в символах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число расширенных символов, найденных в строке определяется [IsExtendedChar](#isextendedchar).  
  
## <a name="isextendedchar"></a> IsExtendedChar
Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *ch*  
 Проверяемый символ  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если символ был расширен, FALSE в противном случае.  
  
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
 *pbSrcData*  
 Буфер, содержащий данные для кодирования.  
  
 *nSrcLen*  
 Длина в байтах для кодирования данных.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в символах *szDest*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 *pszCharSet*  
 Набор знаков, используемый для преобразования.  
  
 *pnNumEncoded*  
 Указатель на переменную, которая при возвращении содержит число небезопасных символов, которые должны были быть преобразован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «Q» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength 
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число байтов данных для кодирования.  
  
 *nCharsetLen*  
 Длина в символах, используется для преобразования символа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, необходимых для буфера, который может содержать закодированные данные из *nSrcLen* байт.  
  
### <a name="remarks"></a>Примечания  
 Кодировки «Q» описан в RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="qpdecode"></a> QPDecode
Декодирует строку данных, которая была закодирована в формате quoted-printable, например предыдущим вызовом [QPEncode](#qpencode).  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pbSrcData*  
 Буфер, содержащий данные для декодирования.  
  
 [in] *nSrcLen*  
 Длина в байтах *pbSrcData*.  
  
 [out] *szDest*  
 Выделенный вызывающим объектом буфер для получения декодированные данные.  
  
 [out] *pnDestLen*  
 Указатель на переменную, которая содержит длину в байтах *szDest*. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
 [in] *dwFlags*  
 Флаги, описывающие, каким образом будет осуществляться преобразование. См. в разделе [флаги ATLSMTP_QPENCODE](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования quoted-printable описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированная строка со *nSrcLen* символов.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования quoted-printable описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
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
 *pbSrcData*  
 Буфер, содержащий данные для кодирования.  
  
 *nSrcLen*  
 Длина в байтах для кодирования данных.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в символах *szDest*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 *dwFlags*  
 ATLSMTP_QPENCODE флаги, описывающие, каким образом будет осуществляться преобразование. 
- ATLSMTP_QPENCODE_DOT Если присутствует точка в начале строки, он будет добавлен к выходу, а также в кодировке.
- Добавляет ATLSMTP_QPENCODE_TRAILING_SOFT `=\r\n` закодированная строка.

Схема кодирования quoted-printable описан в [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt).
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования quoted-printable описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число байтов данных для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, необходимых для буфера, который может содержать закодированные данные из *nSrcLen* байт.  
  
### <a name="remarks"></a>Примечания  
 Схема кодирования quoted-printable описан в RFC 2045 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="uudecode"></a> UUDecode
Декодирует строку данных, которая была закодирована в кодировке UUENCODE например предыдущим вызовом к [UUEncode](#uuencode).  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 *pbSrcData*  
 Строка, содержащая данные для декодирования.  
  
 *nSrcLen*  
 Длина в байтах *pbSrcData*.  
  
 *pbDest*  
 Выделенный вызывающим объектом буфер для получения декодированные данные.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в байтах *pbDest*. Если функция выполняется успешно, переменная получает число байтов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в байтах буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соблюдена спецификация POSIX P1003.2b/D11.  
  
## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength
Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число символов в закодированную строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число байтов, необходимых для буфера, который может содержать декодированная строка со *nSrcLen* символов.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соблюдена спецификация POSIX P1003.2b/D11.  
  
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
 *pbSrcData*  
 Буфер, содержащий данные для кодирования.  
  
 *nSrcLen*  
 Длина в байтах для кодирования данных.  
  
 *szDest*  
 Выделенный вызывающим объектом буфер для получения данных.  
  
 *pnDestLen*  
 Указатель на переменную, которая содержит длину в символах *szDest*. Если функция выполняется успешно, переменная получает количество символов, записанных в буфер. Если функция завершается с ошибкой, переменная получает требуемую длину в символах, буфера.  
  
 *lpszFile*  
 Файл для добавления к заголовку ATLSMTP_UUENCODE_HEADER, заданные в *dwFlags*.  
  
 *dwFlags*  
 Флаги, управляющие поведением этой функции. 
- Кодируется ATLSMTP_UUENCODE_HEADE заголовок.
- Кодируется ATLSMTP_UUENCODE_END окончания.
- Запечатыванием ATLSMTP_UUENCODE_DOT данных будет выполняться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соблюдена спецификация POSIX P1003.2b/D11.  
  
## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength
Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcLen*  
 Число байтов данных для кодирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число символов, необходимых для буфера, который может содержать закодированные данные из *nSrcLen* байт.  
  
### <a name="remarks"></a>Примечания  
 Эта реализация uuencoding соблюдена спецификация POSIX P1003.2b/D11.  
  
### <a name="see-also"></a>См. также  
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)   