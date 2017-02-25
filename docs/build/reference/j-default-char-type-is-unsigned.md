---
title: "/J (тип знака по умолчанию не подписан) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned"
  - "VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned"
  - "/j"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/J - параметр компилятора [C++]"
  - "char - тип данных"
  - "по умолчанию используется символьный тип без знака"
  - "по умолчанию, тип char"
  - "J - параметр компилятора [C++]"
  - "-J - параметр компилятора [C++]"
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /J (тип знака по умолчанию не подписан)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет тип `char` по умолчанию из `signed char` в `unsigned char` и тип `char` нулевым расширяется при расширен в тип `int`.  
  
## Синтаксис  
  
```  
/J  
```  
  
## Заметки  
 Если `char` значение явно объявляется как `signed`, параметр **\/J** не влияет на его и значение расширено знаком при его расширен в тип `int`.  
  
 Параметр **\/J** определяет `_CHAR_UNSIGNED`, используемый вместе с `#ifndef` в файле LIMITS.h для определения диапазона типа `char` по умолчанию.  
  
 В ANSI C и C\+\+ специальная реализация типа `char` не требуется.  Данный параметр рекомендуется использовать при работе с символьными данными, которые будут в дальнейшем переведены и на другие языки, кроме английского.  
  
> [!NOTE]
>  При использовании этого параметра компилятора с ATL\/MFC, ошибка может быть создана.  Хотя можно отключить эту ошибку, указав `_ATL_ALLOW_CHAR_UNSIGNED`, эта ошибка не поддерживается и может работать не всегда.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  В области **Обозреватель решений** откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В диалоговом окне **Окна свойств** проекта, в левой панели в **Свойства конфигурации** разверните узел **C\/C\+\+**, а затем выберите **Командная строка**.  
  
3.  В области **Дополнительные параметры** укажите параметр компиляции **\/J**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md)