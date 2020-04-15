---
title: 'Как: Создать частично надежное приложение (КЗ/CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: 9df3a751f4073472b9495425599aaf43878db99a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364406"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Практическое руководство. Создание приложения с частичным доверием путем удаления зависимости от библиотеки DLL CRT

В этой теме обсуждается, как создать частично доверенное приложение Common Language Runtime с использованием визуального C', удалив зависимость от msvcm90.dll.

Визуальное приложение C', построенное с **/clr,** будет иметь зависимость от msvcm90.dll, который является частью библиотеки C-Runtime. Если вы хотите, чтобы ваше приложение использовалось в частичной доверительной среде, CLR будет применять определенные правила безопасности доступа к коду в вашем DLL. Поэтому необходимо будет удалить эту зависимость, поскольку msvcm90.dll содержит родной код, и политика безопасности доступа к коду не может быть применена к ней.

Если ваше приложение не использует какую-либо функциональность библиотеки C-Runtime и вы хотите удалить зависимость от этой библиотеки из вашего кода, вам придется использовать **/NODEFAULTLIB:msvcmrt.lib** linker опцию и ссылку с либо ptrustm.lib или ptrustmd.lib. Эти библиотеки содержат файлы объектов для инициализации и неинициализации приложения, классы исключений, используемые кодом инициализации, и управляемый код обработки исключений. Ссылка в одной из этих библиотек удалит любую зависимость от msvcm90.dll.

> [!NOTE]
> Порядок неифализации сборки может отличаться для приложений, которые используют библиотеки ptrust. Для обычных приложений сборки обычно выгружаются в обратном порядке, что они загружаются, но это не гарантируется. Для приложений частичного доверия сборки обычно выгружаются в том же порядке, что и загружены. Это также не гарантируется.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Создание частично надежного смешанного (/clr) приложения

1. Чтобы удалить зависимость от msvcm90.dll, необходимо указать связующим, чтобы не включать эту библиотеку с помощью **опции /NODEFAULTLIB:msvcmrt.lib** linker. Для получения информации о том, как это сделать, используя среду разработки Visual Studio или программно, [см.](../build/reference/nodefaultlib-ignore-libraries.md)

1. Добавьте одну из библиотек ptrustm в зависимости ввода ссылок. Используйте ptrustm.lib, если вы строите приложение в режиме выпуска. Для отладки режима используйте ptrustmd.lib. Для получения информации о том, как это сделать, используя среду разработки Visual Studio или программно, [см. Lib Файлы как Linker Вход](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>См. также раздел

[Смешанные (родные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Инициализация смешанных ассамблей](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Поддержка библиотек для смешанных сборок](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/ссылка (Пасс Варианты Для Linker)](../build/reference/link-pass-options-to-linker.md)
