---
title: Сравнение смешанных, чистых и проверяемых компонентов (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cb1b2ba71277415fd1ba5124f6120cc2f2c995d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704715"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Сравнение смешанных, чистых и проверяемых компонентов (C + +/ CLI)

В этом разделе приводится сравнение компонентов в различных **/CLR** режимов компиляции. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

> [!IMPORTANT]
> **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

## <a name="feature-comparison"></a>Сравнение функций

|Функция|Смешанный (/ clr)|Чистые (/ clr: pure)|Безопасный (/ CLR: safe)|Связанные данные|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|Библиотека CRT|Поддерживается|deprecated||[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)|
|MFC И ATL|Поддерживается|||[Настольных приложений MFC](../mfc/mfc-desktop-applications.md) &#124; [Общие сведения о классах](../atl/atl-class-overview.md)|
|Неуправляемые функции|Поддерживается|||[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)|
|Неуправляемые данные|Поддерживается|deprecated||[Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|Может быть вызван из неуправляемых функций|Поддерживается||||
|Поддерживает вызов неуправляемых функций|Поддерживается|deprecated|deprecated|[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|Поддерживает отражение|Только библиотеки DLL|deprecated|deprecated|[Отражение (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>См. также

- [Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)