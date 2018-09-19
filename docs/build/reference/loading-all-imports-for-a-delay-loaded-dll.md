---
title: Загрузка всех импортов для библиотеки DLL, загружаемых с задержкой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29ef1c576af7930e157dafd0f57bf0b8dff49fa6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715589"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Загрузка всех импортов для библиотеки DLL с отложенной загрузкой

**__HrLoadAllImportsForDll** функцию, которая определена в delayhlp.cpp, предписывает компоновщику загрузка всех импортов из библиотеки DLL, который был указан с [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) параметр компоновщика.

Загрузка всех импортов позволяет поместить обработка ошибок в одном месте в коде и не использовать обработку исключений вокруг фактических вызовов операции импорта. Она также позволяет избежать ситуации, когда приложение частично ошибка в процессе, в результате сбоя загрузки потока импорта вспомогательного кода.

Вызов **__HrLoadAllImportsForDll** не изменяет поведение ловушки и ошибка обработки; см. в разделе [обработка ошибок и уведомления](../../build/reference/error-handling-and-notification.md) Дополнительные сведения.

Имя библиотеки DLL, переданного **__HrLoadAllImportsForDll** сравнивается с именем, хранящиеся непосредственно в библиотеки и чувствительно к регистру.

В следующем примере показан вызов **__HrLoadAllImportsForDll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)