---
title: 'Как: Добавление пользовательских средств построения в проекты MSBuild | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efa484e4ad57a3a1f27621e16dddcf90135b7057
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Практическое руководство. Добавление пользовательских средств построения в проекты MSBuild
Пользовательскому средству сборки является определяемой пользователем программа командной строки, связанный с конкретного файла.  
  
 Для конкретного файла укажите в файл проекта (VCXPROJ-файл) из командной строки для выполнения, любые дополнительные входные или выходные файлы и сообщения для отображения. Если **MSBuild** определяет, что выходные файлы устарели по отношению к входным файлам, он выводит сообщение и выполняет программу командной строки.  
  
 Чтобы указать, при выполнении настраиваемого инструмента сборки, используйте один или оба `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементы в файле проекта. Например можно указать выполнение то пользовательский инструмент построения компилятор MIDL и компилятор C/C++. Укажите `CustomBuildBeforeTargets` элемент запустить программу перед запуском конкретного целевого; `CustomBuildAfterTargets` элемент, чтобы выполнить этот инструмент после конкретного целевого; или обоих элементов для запуска средства между выполнением двух целевых объектов. Если не указан ни один из элементов, то пользовательский инструмент построения выполняется в расположении по умолчанию, перед **MIDL** цели.  
  
 Настраиваемые этапы построения и пользовательские средства построения совместно используют сведения, указанные в `CustomBuildBeforeTargets` и `CustomBuildAfterTargets` XML-элементов. Укажите эти целевые объекты один раз в файле проекта.  
  
### <a name="to-add-a-custom-build-tool"></a>Чтобы добавить средство настраиваемого построения  
  
1.  Добавить группу элементов в файле проекта и добавить элемент для каждого входного файла. Укажите команду, дополнительные входные, выходные данные и сообщения в виде метаданных элемента, как показано ниже. В этом примере предполагается, что файл «файл faq.txt» существует в том же каталоге, что и проект.  
  
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
  
1.  Добавьте следующую группу свойств в файл проекта. Необходимо указать хотя бы один из целевых объектов, но другой можно опустить, если вас интересуют только этапа построения выполнение до (или после) конкретного целевого объекта. В этом примере пользовательский этап выполняется после компиляции и перед компоновкой.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Использование MSBuild для создания проекта Visual C++](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Как: использование событий построения в проекты MSBuild](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Практическое руководство. Добавление пользовательского шага сборки в проекты MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)