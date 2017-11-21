---
title: "Ошибка времени выполнения C R6035 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6035
dev_langs: C++
helpviewer_keywords: R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6f0f6e34ef6c95d4c1942cdc1348000213647b0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6035"></a>Ошибка времени выполнения C R6035
Microsoft Visual C++ библиотеки времени выполнения, ошибка R6035 — Модуль в этом приложении инициализация модуля глобальный файл cookie безопасности во время активного как функция, использующая этот файл.  Вызов __security_init_cookie ранее.  
  
 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) должен вызываться перед первым использованием файл cookie глобальной безопасности.  
  
 Файл cookie глобальной безопасности используется для защиты от переполнения буфера в коде, скомпилированном с [/GS (проверка безопасности буфера)](../../build/reference/gs-buffer-security-check.md) и в коде, в котором используются структурированной обработки исключений. По существу при входе в функцию, защищенную от переполнения cookie помещается в стек и при выходе значение в стеке сравнивается с глобальным cookie-файлом. Любое различие между ними указывает, что произошло переполнение буфера, что приводит к немедленному завершению работы программы.  
  
 Ошибка R6035 означает, что вызов `__security_init_cookie` сделана после защищенную функцию. Если нужно продолжить выполнение, так как файл cookie в стеке больше не соответствует глобальному файлу cookie бы обнаружено ложное переполнение буфера.  
  
 Рассмотрим следующий пример DLL. Точки входа библиотеки DLL задано значение DllEntryPoint компоновщика [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md) параметр. Это позволяет обойти инициализацию CRT, в которой, как правило, инициализируется глобальный файл cookie безопасности, поэтому сама Библиотека должна вызвать `__security_init_cookie`.  
  
```  
// Wrong way to call __security_init_cookie  
DllEntryPoint(...) {  
   DllInitialize();  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
  
void DllInitialize() {  
   __security_init_cookie();  
}  
```  
  
 В этом примере возникнет ошибка R6035, поскольку DllEntryPoint использует структурированной обработки исключений и таким образом файл cookie безопасности для определения переполнения буфера. К моменту вызова DllInitialize файл cookie глобальной безопасности уже помещен в стеке.  
  
 В этом примере демонстрируется правильный способ:  
  
```  
// Correct way to call __security_init_cookie  
DllEntryPoint(...) {  
   __security_init_cookie();  
   DllEntryHelper();  
}  
  
void DllEntryHelper() {  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
```  
  
 В этом случае DllEntryPoint не защищена от переполнения буфера (он не локальные буферы строк и не использовать структурированную обработку исключений); Поэтому может безопасно вызывать `__security_init_cookie`. Затем он вызывает вспомогательную функцию, которая защищена.  
  
> [!NOTE]
>  Сообщение об ошибке R6035 — только для созданных x86 отладки CRT, а только для структурированной обработки исключений, но условие ошибки на всех платформах и для всех форм исключение обрабатывает, например обработки исключений C++.  
  
## <a name="see-also"></a>См. также  
 [Комплексные проверки безопасности компилятора](http://go.microsoft.com/fwlink/?linkid=7260)