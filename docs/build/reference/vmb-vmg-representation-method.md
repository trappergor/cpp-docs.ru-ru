---
title: "-vmb, - vmg (метод представления) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vmb
- /vmg
dev_langs: C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a9d64f8b1035f731adef79356d24eeb3e4f7ee3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (метод представления)
Выберите метод, используемый компилятором для представления указателей на члены класса.  
  
 Используйте **/vmb** Если всегда определении класса перед объявлением указателя на член класса.  
  
 Используйте **/vmg** для объявления указателя на член класса перед определением класса. Это может понадобиться при определении членов в двух различных классах, которые ссылаются друг на друга. Для таких взаимно ссылающейся классов одного класса следует вызывать до ее определения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>Примечания  
 Можно также использовать [pointers_to_members](../../preprocessor/pointers-to-members.md) или [ключевые слова наследования](../../cpp/inheritance-keywords.md) в коде, чтобы указать представление указателя.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)