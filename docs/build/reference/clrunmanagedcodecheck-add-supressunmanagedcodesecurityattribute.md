---
title: "-CLRUNMANAGEDCODECHECK (Добавление атрибута SupressUnmanagedCodeSecurityAttribute) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRUNMANAGEDCODECHECK
dev_langs: C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4810da2a1dd24893a1e69a35091b3a7c89b527e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>Параметр /CLRUNMANAGEDCODECHECK (добавление атрибута SupressUnmanagedCodeSecurityAttribute)
**/ Параметр CLRUNMANAGEDCODECHECK** указывает, будет ли компоновщик применять <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> с компоновщиком `PInvoke` вызовы из управляемого кода в собственные библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компоновщик применяет SuppressUnmanagedCodeSecurityAttribute к созданным `PInvoke` вызовов. Когда **/clrunmanagedcodecheck** действует, SuppressUnmanagedCodeSecurityAttribute не применяется.  
  
 Компоновщик только добавляет атрибут к объектам, которые были скомпилированы с **/CLR** или **/CLR: pure**. Компоновщик не создает `PInvoke` вызывает для объектов, скомпилированных с **/CLR: safe**. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md). Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Объект `PInvoke` вызов создается компоновщиком, когда компоновщик не удается найти управляемый символ, удовлетворяющий ссылке от управляемого вызывающего объекта, но можно найти символ для удовлетворения этой ссылки. Дополнительные сведения о `PInvoke`, в разделе [вызов собственных функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Обратите внимание, что при использовании <xref:System.Security.AllowPartiallyTrustedCallersAttribute> в коде, необходимо явно задать **/clrunmanagedcodecheck**. Если изображение содержит атрибуты SuppressUnmanagedCodeSecurity и AllowPartiallyTrustedCallers не потенциальной уязвимости безопасности.  
  
 В разделе [правила написания безопасного кода для неуправляемого кода](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) Дополнительные сведения о последствиях использования SuppressUnmanagedCodeSecurityAttribute.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **Дополнительно** страницу свойств.  
  
5.  Изменить **проверьте неуправляемый код CLR** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)