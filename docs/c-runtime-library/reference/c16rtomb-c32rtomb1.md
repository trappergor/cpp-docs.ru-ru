---
title: "c16rtomb c32rtomb1 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- c16rtomb
- c32rtomb
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs: C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e9e917719c0b980f3ba46e11456e4a47b2a518ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb
Преобразует расширенный символ в кодировке UTF-16 или UTF-32 в многобайтовый массив в текущем языковом стандарте.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `mbchar`  
 Указатель на массив для хранения преобразованного многобайтового символа.  
  
 [in] `wchar`  
 Расширенный символ для преобразования.  
  
 [in, out] `state`  
 Указатель на объект `mbstate_t` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число байтов, сохраняемых в объекте массива `mbchar`, включая все последовательности сдвигов. Если `wchar` не является допустимым расширенным символом, возвращается значение (`size_t`)(-1), `errno` устанавливается в значение `EILSEQ`, а значение `state` не задано.  
  
## <a name="remarks"></a>Примечания  
 Функция `c16rtomb` преобразует символ `wchar` в кодировке UTF-16 в эквивалентную последовательность обычных символов в текущем языковом стандарте. Если `mbchar` не является пустым указателем, функция сохраняет преобразованную последовательность в объекте массива, на который указывает `mbchar`. До `MB_CUR_MAX` байтов сохраняется в `mbchar`, а `state` устанавливается в итоговое состояние многобайтового сдвига.    Если `wchar` является пустым расширенным символом, сохраняется последовательность, требуемая для восстановления изначального состояния сдвига, за которой при необходимости следует символ null, а `state` устанавливается в исходное состояние преобразования. Функция `c32rtomb` идентична, но преобразует символ в формате UTF-32.  
  
 Если `mbchar` является пустым указателем, поведение аналогично вызову функции, которая заменяет внутренний буфер на `mbchar` , а расширенный пустой символ — на `wchar`.  
  
 Объект состояния преобразования `state` позволяет выполнять последующие вызовы этой функции и других перезапускаемых функций, которые сохраняют состояние сдвига многобайтовых выходных символов. При совместном использовании перезапускаемых и неперезапускаемых функций или при вызове `setlocale` между вызовами перезапускаемой функции результаты являются неопределенными.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`c16rtomb`, `c32rtomb`|C, C++: \<uchar.h>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16, mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)