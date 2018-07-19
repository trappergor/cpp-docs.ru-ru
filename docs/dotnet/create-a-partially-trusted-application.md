---
title: 'Как: Создание приложения с частичным доверием (C + +/ CLI) | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a4a0a4b8b1045a9107158c6e67ecdfa7939b6a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109002"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Практическое руководство. Создание приложения с частичным доверием путем удаления зависимости от библиотеки DLL CRT
В этом разделе описывается создание приложения с частичным доверием среды CLR, с помощью Visual C++ путем удаления зависимости от библиотеки msvcm90.dll.  
  
 Приложения Visual C++, созданного с помощью **/CLR** , имеют зависимость от библиотеки msvcm90.dll, которая является частью библиотеки времени выполнения C. Если необходимо, чтобы приложение для использования в среде с частичным доверием, CLR будет применять определенные правилами безопасности доступа кода для библиотеки DLL. Таким образом будет необходимо удалить эту зависимость, поскольку msvcm90.dll содержит машинный код и политика разграничения доступа кода не может быть применены к нему.  
  
 Если приложение не использует функциональные возможности библиотеки времени выполнения C, и вы хотите удалить зависимость от этой библиотеки из кода, необходимо использовать **/NODEFAULTLIB:msvcmrt.lib** компоновщика и компоновку с файлом ptrustm.lib или ptrustmd.lib. Эти библиотеки содержат файлы объектов для инициализации и отмены инициализации приложения, классы исключений используется код инициализации и управляемый код обработки исключений. Связывание в одной из этих библиотек удалит любые зависимости от библиотеки msvcm90.dll.  
  
> [!NOTE]
>  Порядок деинициализации сборки может отличаться для приложений, использующих библиотеки с частичным доверием. Для обычных приложений сборки обычно выгружаются в порядке, обратном порядку их загрузки, но это не гарантируется. Для приложений с частичным доверием сборки обычно выгружаются в том же порядке, в котором они были загружены. Это, кроме того, не гарантируется.  
  
### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Создание с частичным доверием смешанного (/ clr) приложения  
  
1.  Чтобы удалить зависимость от библиотеки msvcm90.dll, необходимо указать компоновщику не включать эту библиотеку с помощью **/NODEFAULTLIB:msvcmrt.lib** компоновщика. Сведения о том, как это сделать с помощью среды разработки Visual Studio или программным способом см. [/NODEFAULTLIB (пропуск библиотек)](../build/reference/nodefaultlib-ignore-libraries.md).  
  
2.  Добавьте одну из библиотек ptrustm для компоновщика. При построении приложения в режиме выпуска следует используйте библиотеку ptrustm.lib. В режиме отладки используйте ptrustmd.lib. Сведения о том, как это сделать с помощью среды разработки Visual Studio или программным способом см. [. LIB-файл в качестве входных данных компоновщика](../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Инициализация смешанных сборок](../dotnet/initialization-of-mixed-assemblies.md)   
 [Поддержка библиотек для смешанных сборок](../dotnet/library-support-for-mixed-assemblies.md)   
 [/link (передача параметров компоновщику)](../build/reference/link-pass-options-to-linker.md)   
