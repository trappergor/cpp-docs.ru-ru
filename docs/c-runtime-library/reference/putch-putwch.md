---
title: "_putch, _putwch | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _putwch
- _putch
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _putch
- putwch
- _putwch
dev_langs:
- C++
helpviewer_keywords:
- _putch function
- characters, writing
- putwch function
- _putwch function
- putch function
- console, writing characters to
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75094625553a5e080c9e1b4ec6a1f96a7a76d9b7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="putch-putwch"></a>_putch, _putwch
Записывает символ в строку.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _putch(  
int c   
);  
wint_t _putwch(  
   wchar_t c  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется вывести.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `c` в случае успешного выполнения. Если функция `_putch` завершается с ошибкой, она возвращает `EOF`; если функция **_putwch** завершается с ошибкой, она возвращает **WEOF**.  
  
## <a name="remarks"></a>Примечания  
 Эти функции записывают символ `c` напрямую в консоль (без буферизации). В Windows NT функция **_putwch** записывает символы Юникода, используя текущие настройки языкового стандарта консоли.  
  
 Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков. Дополнительные сведения см. в разделах `_putch_nolock`, `_putwch_nolock`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|**_puttch**|`_putch`|`_putch`|**_putwch**|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_putch`|\<conio.h>|  
|**_putwch**|\<conio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример для [_getch](../../c-runtime-library/reference/getch-getwch.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)