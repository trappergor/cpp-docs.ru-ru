---
title: Преимущества и недостатки метода, используемого для ссылки на CRT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1962b2db987e34a1f0d18fa863473a20f9da7c9d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084267"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Преимущества и недостатки метода, используемого для ссылки на CRT

Проект можно связать с CRT, динамически или статически. В следующей таблице описаны преимущества и недостатки, связанные с выбором подходящего метода.

|Метод|Преимущество|Компромисс|
|------------|-------------|--------------|
|Статическая компоновка с библиотекой CRT<br /><br /> (**Библиотеки времени выполнения** присвоено **Single-threaded**)|В системе, где будет выполняться изображение CRT DLL не требуется.|Около 25K код запуска добавляется в образ, незначительно увеличив его размер.|
|Динамическое связывание с CRT<br /><br /> (**Библиотеки времени выполнения** присвоено **многопоточных**)|Образ не требует код запуска CRT, поэтому гораздо меньше.|В системе, образ должен быть CRT DLL.|

Раздел [связывание с CRT в проект ATL](../atl/linking-to-the-crt-in-your-atl-project.md) описывается выберите способ для добавления ссылки на CRT.

## <a name="see-also"></a>См. также

[Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../build/run-time-library-behavior.md)<br/>
[Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)

