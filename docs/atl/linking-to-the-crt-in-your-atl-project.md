---
title: Связывание с CRT в ATL-проект | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DllMainCRTStartup
- wWinMainCRTStartup
- WinMainCRTStartup
dev_langs:
- C++
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0d93f8770ebbd893491c0e8b8eed239396e00a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356387"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>Связывание с CRT в ATL-проект
[Библиотеки времени выполнения C](../c-runtime-library/crt-library-features.md) (CRT) предоставляют множество полезных функций, которые можно упростить программирование гораздо во время разработки ATL. Все проекты ATL связь с библиотекой CRT. Вы увидите преимущества и недостатки связывания метода в [преимуществами и недостатками метод, используемый для связи с этой библиотекой CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>Связывание с CRT на образа программы эффекты  
 Если статическая компоновка с библиотекой CRT, код из CRT помещается в исполняемый образ, и необходимо иметь DLL CRT, которые присутствуют в системе для запуска вашего образа. При компоновке с этой библиотекой CRT динамически, ссылки на код в библиотеке DLL CRT, помещаются в образ, но не сам код. Чтобы образ для запуска данной системы должны присутствовать на этой системе CRT DLL. Даже если динамически связывать с этой библиотекой CRT, возможно, вам можно статически связать некоторый код (например, **DllMainCRTStartup**).  
  
 При связывании изображения, явно или неявно указываются точки входа, который будет вызывать после загрузки образа операционной системы. Для DLL-Библиотеки, является точкой входа по умолчанию **DllMainCRTStartup**. Для EXE-файла, это **случае**. Можно переопределить значение по умолчанию с помощью параметра компоновщика/ENTRY. Библиотека CRT предоставляет реализацию для **DllMainCRTStartup**, **случае**, и **wWinMainCRTStartup** (Юникод точку входа для EXE-файла). Эти точки входа, предоставляемых системой CRT вызывать конструкторы для глобальных объектов и инициализации других структур данных, которые используются в некоторых функций CRT. Этот код запуска добавляет около 25 КБ в образ, если статическое связывание. Если связана динамически, большая часть кода находится в DLL-Библиотеке, поэтому остается небольшой размер вашего образа.  
  
 Дополнительные сведения см. в разделе компоновщика [/Entry (символ точки входа)](../build/reference/entry-entry-point-symbol.md).  
  
## <a name="optimization-options"></a>Параметры оптимизации  
 С помощью параметра компоновщика/OPT: NOWIN98 можно еще более уменьшить элемент управления ATL по умолчанию, 10 КБ за счет снижения увеличена загрузка в системе Windows 98. Дополнительные сведения о связывании параметров см. в разделе [/OPT (оптимизации)](../build/reference/opt-optimizations.md).  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../build/run-time-library-behavior.md)

