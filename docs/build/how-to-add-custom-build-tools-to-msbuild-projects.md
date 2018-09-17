---
title: 'Практическое: Добавление пользовательских средств построения в проекты MSBuild | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e06a2a545862c0fa9cfdcf6311334ecc86de2bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714406"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Практическое руководство. Добавление пользовательских средств построения в проекты MSBuild

Пользовательскому средству сборки — определяемые пользователем программа командной строки, связанный с определенным файлом.

Для конкретного файла укажите в файл проекта (с расширением VCXPROJ) командной строки для выполнения, любые дополнительные входные или выходные файлы и сообщения для отображения. Если **MSBuild** определяет, что выходные файлы неактуальны по отношению к входным файлам, он отображает сообщение и выполняет программу командной строки.

Чтобы указать, при выполнении настраиваемого инструмента сборки, используйте один или оба `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементов в файле проекта. Например может указать, что ваш настраиваемый инструмент сборки запускаться после компилятора MIDL и перед компилятор C/C++. Укажите `CustomBuildBeforeTargets` элемент запустить программу перед выполнением конкретного целевого объекта; `CustomBuildAfterTargets` элемент для выполнения после конкретной цели; средство или оба элемента, чтобы запустить средство между выполнением двух целевых объектов. Если не указан ни один из элементов, то пользовательский инструмент построения выполняется в расположении по умолчанию, перед **MIDL** целевой объект.

Настраиваемые этапы построения и пользовательских средств построения совместного использования сведений, указанных в `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементов. Укажите эти целевые объекты один раз в файле проекта.

### <a name="to-add-a-custom-build-tool"></a>Чтобы добавить настраиваемый инструмент сборки

1. Добавить группу элементов в файл проекта и добавление элемента для каждого входного файла. Укажите команду, дополнительные входные данные, выходные данные и сообщения как метаданные элементов, как показано ниже. В этом примере предполагается, что файл «файл faq.txt» существует в каталоге проекта.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Чтобы определить, где в построении пользовательских средств построения будет выполняться

1. Добавьте следующие группы свойств в файл проекта. Необходимо указать хотя бы один из целевых объектов, но другой можно опустить, если вы заинтересованы только в этапа построения выполняться до (или после) конкретного целевого объекта. В этом примере пользовательский этап выполняется после компиляции и перед компоновкой.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>См. также

[Пошаговое руководство. Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Практическое руководство. Использование событий сборки в проектах MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[Практическое руководство. Добавление пользовательского шага сборки в проекты MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)