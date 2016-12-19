---
title: "Параметр /CLRUNMANAGEDCODECHECK (добавление атрибута SupressUnmanagedCodeSecurityAttribute) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRUNMANAGEDCODECHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRUNMANAGEDCODECHECK - параметр компоновщика"
  - "-CLRUNMANAGEDCODECHECK - параметр компоновщика"
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметр /CLRUNMANAGEDCODECHECK (добавление атрибута SupressUnmanagedCodeSecurityAttribute)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр **\/CLRUNMANAGEDCODECHECK** используется для добавления атрибута <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> к создаваемым с помощью компоновщика вызовам `PInvoke` из управляемого кода в машинные библиотеки DLL.  
  
## Синтаксис  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## Заметки  
 По умолчанию компоновщик применяет SuppressUnmanagedCodeSecurityAttribute к создаваемым им вызовам `PInvoke`.  Когда действует **\/CLRUNMANAGEDCODECHECK**, SuppressUnmanagedCodeSecurityAttribute не применяется.  
  
 При компоновке этот атрибут добавляется только к объектам, скомпилированным с использованием параметра **\/clr** или **\/clr:pure**.  Вызовы `PInvoke` для объектов, скомпилированных с использованием параметра **\/clr:safe**, не создаются.  Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Вызов `PInvoke` создается при компоновке в том случае, если не удается найти управляемый символ, удовлетворяющий ссылке от управляемого вызывающего объекта, но при этом существует соответствующий неуправляемый символ.  Дополнительные сведения о `PInvoke` см. в разделе [Вызов неуправляемых функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Обратите внимание, что при использовании в коде атрибута <xref:System.Security.AllowPartiallyTrustedCallersAttribute> следует явно задать параметр **\/CLRUNMANAGEDCODECHECK**.  Одновременное включение в образ атрибутов SuppressUnmanagedCodeSecurity и AllowPartiallyTrustedCallers представляет собой потенциальную угрозу безопасности.  
  
 Дополнительные сведения о применении атрибута SuppressUnmanagedCodeSecurityAttribute см. в разделе [Security Optimizations](http://msdn.microsoft.com/ru-ru/cf255069-d85d-4de3-914a-e4625215a7c0).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Дополнительно**.  
  
5.  Измените значение свойства **Проверка среды CLR на неуправляемый код**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)