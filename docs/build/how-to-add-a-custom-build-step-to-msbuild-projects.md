---
title: 'Практическое: Добавление пользовательского шага построения в проекты MSBuild | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca8206024f4fbaf38b8161a9e12672782551db83
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712183"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Практическое руководство. Добавление пользовательского шага построения в проекты MSBuild

Настраиваемый этап построения — это этап, определяемые пользователем, в сборке. Настраиваемый этап построения ведет себя подобно любому другому *средство командной строки для* шаг, такие как стандартный этап инструмента компиляции или компоновки.

Укажите настраиваемый этап построения в файле проекта (с расширением VCXPROJ). Этот шаг можно указать командную строку для выполнения, любые дополнительные входные или выходные файлы и сообщения для отображения. Если **MSBuild** определяет, что выходные файлы неактуальны по отношению к входным файлам, он отображает сообщение и выполняет команду.

Чтобы указать, расположение настраиваемой сборки шаг в последовательности целевые объекты сборки, используйте один или оба `CustomBuildAfterTargets` и `CustomBuildBeforeTargets` XML-элементов в файле проекта. Например может указать, что настраиваемый этап сборки выполняется после назначения средство ссылки и перед целевым объектом инструмента манифеста. Фактический набор доступных целевых объектов зависит от конкретного построения.

Укажите `CustomBuildBeforeTargets` элемент для выполнения настраиваемого этапа сборки, перед запуском конкретной цели, `CustomBuildAfterTargets` элемент для выполнения на шаге после выполнения конкретной цели, или оба элементы, выполняемые на этапе между запуском. Если не указан ни один из элементов, то пользовательский инструмент построения выполняется в расположении по умолчанию, то есть после **ссылку** целевой объект.

Настраиваемые этапы построения и пользовательских средств построения совместного использования сведений, указанных в `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементов. Таким образом укажите эти целевые объекты только один раз в файле проекта.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Для определения выполняемых настраиваемого этапа сборки

1. Добавьте группу свойств в файл проекта. В этой группе свойств укажите команду, входные и выходные данные и сообщения, как показано в следующем примере. В этом примере создает CAB-файл в файле main.cpp, созданный в [Пошаговое руководство: использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(TargetFileName)</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Чтобы определить, где в построении настраиваемый этап сборки будет выполняться

1. Добавьте следующие группы свойств в файл проекта. Можно указать оба целевых объекта, или один можно опустить, если вам требуется пользовательский этап для выполнения до или после конкретной цели. В этом примере указывает **MSBuild** выполнение пользовательского шага после этапа компиляции, но перед этапом компоновки.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>См. также

[Пошаговое руководство. Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Практическое руководство. Использование событий сборки в проектах MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[Практическое руководство. Добавление пользовательских средств сборки в проекты MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)