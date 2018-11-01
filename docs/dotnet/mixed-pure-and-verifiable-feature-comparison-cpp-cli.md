---
title: Сравнение смешанных, чистых и проверяемых компонентов (C + +/ CLI)
ms.date: 11/04/2016
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
ms.openlocfilehash: 81fcf986ee68f5f8f64c8070bb992fa1cda1683b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482082"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Сравнение смешанных, чистых и проверяемых компонентов (C + +/ CLI)

В этом разделе приводится сравнение возможностей в различных **/CLR** режимов компиляции. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

> [!IMPORTANT]
> **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

## <a name="feature-comparison"></a>Сравнение функций

|Функция|Смешанный (/ clr)|Чистые (/ clr: pure)|Safe (/ CLR: safe)|Связанные сведения|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|Библиотека CRT|Поддерживается|deprecated||[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)|
|MFC/ATL|Поддерживается|||[Настольных приложений MFC](../mfc/mfc-desktop-applications.md) &#124; [Обзор класса](../atl/atl-class-overview.md)|
|Неуправляемые функции|Поддерживается|||[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)|
|Неуправляемые данные|Поддерживается|deprecated||[Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|Может быть вызван из неуправляемых функций|Поддерживается||||
|Поддерживает вызов неуправляемых функций|Поддерживается|deprecated|deprecated|[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|Поддерживает отражения|Только библиотеки DLL|deprecated|deprecated|[Отражение (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>См. также

- [Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)