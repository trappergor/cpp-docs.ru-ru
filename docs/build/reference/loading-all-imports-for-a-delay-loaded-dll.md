---
title: Загрузка всех импортов для библиотеки DLL с отложенной загрузкой
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: e855b648dc7a9ee0670c3704a11aa1897a238403
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811918"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Загрузка всех импортов для библиотеки DLL с отложенной загрузкой

**__HrLoadAllImportsForDll** функцию, которая определена в delayhlp.cpp, предписывает компоновщику загрузка всех импортов из библиотеки DLL, который был указан с [/DELAYLOAD](delayload-delay-load-import.md) параметр компоновщика.

Загрузка всех импортов позволяет поместить обработка ошибок в одном месте в коде и не использовать обработку исключений вокруг фактических вызовов операции импорта. Она также позволяет избежать ситуации, когда приложение частично ошибка в процессе, в результате сбоя загрузки потока импорта вспомогательного кода.

Вызов **__HrLoadAllImportsForDll** не изменяет поведение ловушки и ошибка обработки; см. в разделе [обработка ошибок и уведомления](error-handling-and-notification.md) Дополнительные сведения.

Имя библиотеки DLL, переданного **__HrLoadAllImportsForDll** сравнивается с именем, хранящиеся непосредственно в библиотеки и чувствительно к регистру.

В следующем примере показан вызов **__HrLoadAllImportsForDll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](linker-support-for-delay-loaded-dlls.md)
