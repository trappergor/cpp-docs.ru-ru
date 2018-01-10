---
title: "-CLRIMAGETYPE (указание типа образа среды CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d8edd6c9e62456e54ac6228f25d7f923a6813c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (указание типа образа среды CLR)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Примечания  
 Компоновщик принимает собственных объектов, а также MSIL объекты, которые были скомпилированы с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), / CLR: pure или/CLR: safe. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать. При передаче смешанных объектов в той же сборки, является проверяемости выходного файла по умолчанию, равное минимальному уровню проверяемости входных модулей. Например если передать компоновщику безопасный и чистый модуль, выходной файл будет чистым. Если передать образ в машинном коде и образ смешанного режима (скомпилированный с помощью **/CLR**), полученное изображение будет смешанного режима.  
  
 / CLRIMAGETYPE можно использовать для указания более низкий уровень проверяемости, если необходимые условия.  
  
 В .NET 4.5 / CLRIMAGETYPE поддерживает параметр SAFE32BITPREFERRED. Это задает — в заголовке PE образа — флаги, указывающие, что MSIL объекты безопасности и может быть запуска на всех платформах, но являются предпочтительными, выполнение 32-разрядных сред. Этот параметр позволяет приложению для выполнения на платформах ARM и также указывает, что оно должно запускаться в режиме WOW64 на 64-разрядных операционных системах, вместо того чтобы использовать среду выполнения 64-разрядной.  
  
 Когда .exe, который был скомпилирован с помощью **/CLR** или **/CLR: pure** выполняется на 64-разрядной операционной системе, приложение запускается в режиме WOW64, который позволяет 32-разрядное приложение для запуска в 64-разрядной операционной системе. По умолчанию .exe, который компилируется с помощью **/CLR: safe** работает по расписанию с поддержкой 64-разрядной операционной системы. Однако это возможно, что ваш безопасное приложение может загрузить 32-разрядный компонент. В этом случае безопасный образ, выполняющийся под поддержкой 64-разрядной операционной системы будет сбой при загрузке 32-разрядного приложения. Чтобы убедиться, что безопасный образ продолжает выполняться при загрузке 32-разрядный компонент в 64-разрядной операционной системе, используйте параметр /CLRIMAGETYPE:SAFE32BITPREFERRED. Если код не имеет на платформах ARM, можно указать / CLRIMAGETYPE: PURE параметр для изменения метаданных (.corflags), пометив его для запуска в режиме WOW64 (и подстановка ваш символ записи):  
  
 **cl /clr:safe t.cpp /link /clrimagetype:pure /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 Сведения о том, как определить тип образа среды файла CLR, см. в разделе [/CLRHEADER](../../build/reference/clrheader.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **Дополнительно** страницу свойств.  
  
5.  Изменить **тип образа среды CLR** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)