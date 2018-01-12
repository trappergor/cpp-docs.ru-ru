---
title: "Как: Добавление пользовательского шага построения в проекты MSBuild | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.howto.addcustombuildstep
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d664b9fad6a9ec67dc009a90171119036dc13cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Практическое руководство. Добавление пользовательского шага построения в проекты MSBuild
Этап настраиваемого построения — это определяемые пользователем этап в построении. Этап настраиваемого построения ведет себя как любой другой *средство командной строки* шаг, такие как стандартный этап инструмента компиляции или компоновки.  
  
 Укажите этап настраиваемого построения в файл проекта (VCXPROJ). Этот шаг можно указать командную строку для выполнения все дополнительные входные или выходные файлы и сообщения для отображения. Если **MSBuild** определяет, что выходные файлы устарели по отношению к входным файлам, он выводит сообщение и выполняет команду.  
  
 Чтобы указать расположение настраиваемого построения шага в последовательности целевых объектов построения, используйте один или оба `CustomBuildAfterTargets` и `CustomBuildBeforeTargets` XML-элементы в файле проекта. Например можно указать, что этап настраиваемого построения выполняется после целевого объекта инструмента компоновки и перед целевым объектом инструмента манифеста. Фактический набор доступных целевых объектов зависит от конкретного построения.  
  
 Укажите `CustomBuildBeforeTargets` элемент для выполнения пользовательского шага построения перед выполнением конкретного целевого `CustomBuildAfterTargets` запуском конкретного целевого элемента или обоих элементов, чтобы выполнить шаг запуском. Если не указан ни один из элементов, то пользовательский инструмент построения выполняется в расположении по умолчанию, то есть после **ссылку** цели.  
  
 Настраиваемые этапы построения и пользовательские средства построения совместно используют сведения, указанные в `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементов. Таким образом укажите эти целевые объекты только один раз в файле проекта.  
  
### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Чтобы определить, выполняемых пользовательского шага построения  
  
1.  Добавьте группу свойств в файл проекта. В этой группе свойств укажите команду, входные и выходные данные и сообщения, как показано в следующем примере. Этот пример создает CAB-файл из файла main.cpp, созданного в [Пошаговое руководство: использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  
  
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
  
1.  Добавьте следующую группу свойств в файл проекта. Можно указать оба целевых объектов или один можно опустить, если требуется пользовательский этап для выполнения до или после конкретного целевого объекта. В этом примере сообщает **MSBuild** следует выполнять пользовательский этап после этапа компиляции, но перед этапом компоновки.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Как: использование событий построения в проекты MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Практическое руководство. Добавление пользовательских средств сборки в проекты MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)