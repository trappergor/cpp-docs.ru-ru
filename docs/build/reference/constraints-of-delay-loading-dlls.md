---
title: Ограничения библиотек DLL, загружаемых с задержкой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40774d6307eb9b423ebd4fd303a48acbd87eda24
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572112"
---
# <a name="constraints-of-delay-loading-dlls"></a>Ограничения библиотек DLL, загружаемых с задержкой
Существует ряд ограничений, связанных с отложенной загрузкой файлов импорта.  
  
-   Файлы импорта данных не поддерживаются. Существует обходной путь, заключающийся в явном импорте данных с помощью методов `LoadLibrary` (или `GetModuleHandle` после того, как вспомогательная функция отложенной загрузки загрузила библиотеку DLL) и `GetProcAddress`.  
  
-   Отложенная загрузка Kernel32.dll не поддерживается. Эта библиотека DLL необходима для того, чтобы вспомогательные подпрограммы отложенной загрузки могли выполнить отложенную загрузку.  
  
-   [Привязка](../../build/reference/binding-imports.md) записи переадресованных точек не поддерживается.  
  
-   Отложенная загрузка библиотеки DLL может изменить поведение процесса, если в точке входа библиотеки DLL, загружаемой с задержкой, осуществляется инициализация процессов. Другие варианты включают статическая память TLS (локальное хранилище потока), объявленные с помощью [__declspec(thread)](../../cpp/thread.md), который не обрабатывается, когда библиотека DLL загружается через `LoadLibrary`. Тем не менее, как в статических библиотеках DLL, так и в библиотеках DLL, загружаемых с задержкой, доступна для использования динамическая память TLS, реализуемая с помощью функций `TlsAlloc`, `TlsFree`, `TlsGetValue` и `TlsSetValue`.  
  
-   Статические (глобальные) указатели импортируемых функций потребуется инициализировать заново после первого вызова соответствующих функций. Причина в том, что при первом вызове указатель функции указывает на преобразователь.  
  
-   В настоящее время не существует способа отложить загрузку отдельных подпрограмм в библиотеке DLL при использовании нормального механизма импорта.  
  
-   Пользовательские соглашения о вызовах (например использование условных кодов в архитектурах x86) не поддерживаются. Кроме того, регистры с плавающей запятой не сохраняются ни на одной платформе. Если пользовательская вспомогательная подпрограмма или обработчик используют типы данных с плавающей запятой, то в них потребуется выполнить полное сохранение и восстановление состояния регистров с плавающей запятой на компьютерах, где в соглашениях о вызовах для передачи параметров с плавающей запятой используются регистры. Следует осторожно подходить к отложенной загрузке библиотеки DLL времени выполнения (CRT), если в программе вызываются функции CRT, принимающие параметры с плавающей запятой через стек арифметического сопроцессора (NDP) во вспомогательной функции.  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [Функции LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [Функция GetModuleHandle](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress-функция](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [Функцию TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)   
 [Функция TlsFree](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsfree)   
 [Функция TlsGetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)   
 [Функция TlsSetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)