---
title: "_inp, _inpw, _inpd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_inp"
  - "_inpw"
  - "_inpd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "inpd"
  - "_inp"
  - "_inpw"
  - "_inpd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_inp - функция"
  - "_inpd - функция"
  - "_inpw - функция"
  - "Ввод и вывод [CRT], порт"
  - "inp - функция"
  - "inpd - функция"
  - "inpw - функция"
  - "порты, процедуры ввода и вывода"
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _inp, _inpw, _inpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вводит из порта байт \(`_inp`\), слово \(`_inpw`\) или двойное слово \(`_inpd`\).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### Параметры  
 `port`  
 Номер порта ввода\-вывода.  
  
## Возвращаемое значение  
 Эти функции возвращают байт, слово или двойное слово, прочитанное из порта `port`. Ошибка не возвращается.  
  
## Заметки  
 Функции `_inp`, `_inpw` и `_inpd` считывают из указанного порта байт, слово и двойное слово соответственно. Входное значение может быть любым беззнаковым коротким целым числом в диапазоне от 0 до 65535.  
  
 Поскольку эти функции производят чтение непосредственно из портов ввода\-вывода, они не могут использоваться в пользовательском коде в Windows NT, Windows 2000, Windows XP и Windows Server 2003.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_inp`|\<conio.h\>|  
|`_inpw`|\<conio.h\>|  
|`_inpd`|\<conio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [\_outp, \_outpw, \_outpd](../Topic/_outp,%20_outpw,%20_outpd.md)