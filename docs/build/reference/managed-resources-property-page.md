---
title: страница свойств управляемых ресурсов
ms.date: 08/28/2019
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 14802996e63392bfb5fcc22096ef5f3d9db197c2
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177529"
---
# <a name="managed-resources-property-page"></a>страница свойств управляемых ресурсов

На странице свойств **управляемые ресурсы** отображаются следующие свойства компилятора управляемых ресурсов [Resgen. exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) при использовании ресурсов .NET в C++программах/CLI:

- **Логическое имя ресурса**

   Указывает *логическое имя* для созданного промежуточного файла RESOURCES. Логическое имя используется для загрузки ресурса. Если логическое имя не указано, вместо него используется имя файла ресурсов (RESX).

- **Имя выходного файла**

   Указывает имя окончательного выходного файла, в который направляется этот файл ресурсов (RESX).

- **Локализованные ресурсы по умолчанию**

   Указывает, направляется ли данный файл RESX в ресурсы по умолчанию либо во вспомогательную библиотеку DLL.

Сведения о том, как получить доступ к странице свойств **управляемых ресурсов** , см. [в разделе Задание C++ свойств компилятора и сборки в Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>См. также

[Использование компилятора ресурсов (командная строка RC)](/windows/win32/menurc/using-rc-the-rc-command-line-)<br>
[C++Справочник по страницам свойств проекта](property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (внедрение управляемого ресурса)](assemblyresource-embed-a-managed-resource.md)
