---
title: Практическое руководство. Создание приложения с частичным доверием (C + +/ CLI)
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
ms.openlocfilehash: afdfb8ca11753d7def9d7da6f431082b1a90c345
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743757"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Практическое руководство. Создание приложения с частичным доверием путем удаления зависимости от библиотеки DLL CRT

В этом разделе описывается создание приложения с частичным доверием среда CLR, с помощью Visual C++ путем удаления зависимости от библиотеки msvcm90.dll.

Приложения Visual C++, созданных с помощью **/CLR** , имеют зависимость от библиотеки msvcm90.dll, которая является частью библиотеки времени выполнения C. Если требуется, чтобы приложение для использования в среде с частичным доверием, CLR будет применять определенные правила безопасности кода доступа к библиотеке DLL. Таким образом его будет необходимо удалить эту зависимость, поскольку msvcm90.dll содержит машинный код и политика разграничения доступа кода не может быть применены к нему.

Если приложение не использует функциональные возможности библиотеки времени выполнения C, и вы хотите удалить зависимость от этой библиотеки из кода, необходимо использовать **/NODEFAULTLIB:msvcmrt.lib** параметр компоновщика и компоновку с файлом ptrustm.lib или ptrustmd.lib. Эти библиотеки содержат файлы объектов для инициализации и деинициализации приложения, классы исключений используется код инициализации и управляемый код обработки исключений. Компоновка в одной из этих библиотек приведет к удалению любых зависимостей от msvcm90.dll.

> [!NOTE]
>  Порядок деинициализации сборки может отличаться для приложений, использующих библиотеки с частичным доверием. Для обычных приложений сборки обычно выгружаются в порядке, обратном порядку их загрузки, но это не гарантируется. Для приложений с частичным доверием сборки обычно выгружаются в том же порядке, в котором они были загружены. Это, кроме того, не гарантируется.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Для создания с частичным доверием смешанный (/ clr) приложения

1. Чтобы удалить зависимость от библиотеки msvcm90.dll, необходимо указать компоновщику не включать эту библиотеку с помощью **/NODEFAULTLIB:msvcmrt.lib** параметр компоновщика. Сведения о том, как это сделать с помощью среды разработки Visual Studio или программными средствами, см. в разделе [/NODEFAULTLIB (Ignore Libraries)](../build/reference/nodefaultlib-ignore-libraries.md).

1. Добавьте одну из библиотек ptrustm компоновщика. Если вы создаете приложение в режиме выпуска следует используйте библиотеку ptrustm.lib. Для режима отладки используйте ptrustmd.lib. Сведения о том, как это сделать с помощью среды разработки Visual Studio или программными средствами, см. в разделе [. LIB-файл в качестве входных данных компоновщика](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>См. также

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Поддержка библиотек для смешанных сборок](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (передача параметров компоновщику)](../build/reference/link-pass-options-to-linker.md)
