---
title: Связывание с CRT в ATL-проект | Документация Майкрософт
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
ms.openlocfilehash: fad8209c680a782bd9800215e1e0affc7e2a98c8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852501"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>Связывание с CRT в ATL-проект
[Библиотек времени выполнения C](../c-runtime-library/crt-library-features.md) (CRT) предоставляют множество полезных функций, которые могут упростить программирование во время разработки ATL. Все проекты ATL связь с библиотекой CRT. Вы увидите, преимущества и недостатки связывания метод в [преимуществах и недостатках метод, используемый для ссылки на CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>Последствия связывание с CRT в образе программы  
 При статической компоновке с библиотекой CRT, код из CRT помещается в исполняемый образ, и необходимо иметь DLL CRT, которые присутствуют в системе, чтобы запустить образ. Динамически при компоновке с библиотекой CRT, ссылки на код в CRT DLL, помещаются в образ, но не сам код. Чтобы ваш образ для выполнения в заданной системе CRT DLL необходимо наличие в этой системе. Даже когда динамически связывать с библиотекой CRT, возможно, вам может статически связан некоторый код (например, `DllMainCRTStartup`).  
  
 При связывании образ, вы явно или неявно указать точку входа, который будет вызывать после загрузки образа операционной системы. Для библиотеки DLL, точка входа по умолчанию является `DllMainCRTStartup`. Для exe-ФАЙЛ, это `WinMainCRTStartup`. Можно переопределить значение по умолчанию параметр компоновщика/ENTRY. CRT предоставляет реализацию для `DllMainCRTStartup`, `WinMainCRTStartup`, и `wWinMainCRTStartup` (Юникода точка входа для EXE-файла). Этих точек входа, предоставляемых системой CRT вызывать конструкторы для глобальных объектов и инициализации других структур данных, которые используются некоторые функции CRT. Этот код запуска добавляет около 25K изображения в том случае, если он связан, статически. Если связана динамически, большая часть кода находится в библиотеку DLL, поэтому остается небольшой размер вашего образа.  
  
 Дополнительные сведения см. в разделе компоновщика [/Entry (символ точки входа)](../build/reference/entry-entry-point-symbol.md).  
  
## <a name="optimization-options"></a>Параметры оптимизации  
 С помощью параметра компоновщика/OPT: NOWIN98 можно еще больше сократить элемент управления ATL по умолчанию, 10 K в ущерб категориям из увеличить загрузку в системах Windows 98. Дополнительные сведения о связывании параметров см. в разделе [/OPT (оптимизации)](../build/reference/opt-optimizations.md).  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../build/run-time-library-behavior.md)

