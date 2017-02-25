---
title: "_set_controlfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_controlfp"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_controlfp"
  - "_set_controlfp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_controlfp - функция"
  - "функции с плавающей запятой, задание контрольного слова"
  - "set_controlfp - функция"
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _set_controlfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает управляющее слово с плавающей точкой.  
  
## Синтаксис  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### Параметры  
 `newControl`  
 Значения бит в новом управляющем слове.  
  
 `mask`  
 Маска для установки битов нового управляющего слова.  
  
## Возвращаемое значение  
 Нет.  
  
## Заметки  
 `_set_controlfp` аналогична `_control87`, но она задает только управляющее слово с плавающей точкой в `newControl`.  Биты в значениях указывают состояние управляющего слова с плавающей точкой.  Состояние управляющего слова с плавающей точкой позволяет программе изменить точность, округление и режимы бесконечности математического пакета для значений с плавающей точкой.  Можно также использовать `_set_controlfp` для маскирования и демаскирования исключений с плавающей точкой.  Для получения дополнительной информации см. [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md).  
  
 Эту функцию не рекомендуется использовать при компилировании с [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) или `/clr:pure`, поскольку среда CLR поддерживает только точность чисел с плавающей точкой по умолчанию.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Совместимость|  
|------------------|----------------------------|-------------------|  
|`_set_controlfp`|\<float.h\>|только для процессоров x86|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)