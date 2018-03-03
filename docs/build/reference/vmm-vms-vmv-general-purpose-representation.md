---
title: "-vmm, — виртуальные машины, - vmv (представление общего назначения) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vms
- /vmm
- /vmv
dev_langs:
- C++
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d54ea3cabbbe631006cc22a80fdbf500585ff20f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms и /vmv (представление общего назначения)
Используется, когда [/vmb, / vmg (метод представления)](../../build/reference/vmb-vmg-representation-method.md) выбран в качестве [метод представления](../../build/reference/vmb-vmg-representation-method.md). Эти параметры указывают модель наследования определения класса, но не обнаружена.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## <a name="remarks"></a>Примечания  
 Данные параметры описаны в следующей таблице.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**/ VMM**|Указывает наиболее общее представление указателя на член класса, в котором используется множественное наследование.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **multiple_inheritance**.<br /><br /> Это представление больше, чем, необходимого для одиночного наследования.<br /><br /> Если модель наследования определения класса, для которой объявлен указатель на член является виртуальной, компилятор создает ошибку.|  
|**/ vms**|Указывает наиболее общее представление указателя на член класса в котором использует без наследования или одиночное наследование.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **одиночного наследования**.<br /><br /> Это наименьшее возможное представление указателя на член класса.<br /><br /> Если модель наследования определения класса, для которой объявлен указатель на член является несколькими или виртуальными, компилятор создает ошибку.|  
|**/ vmv**|Указывает наиболее общее представление указателя на член класса, в котором используется виртуальное наследование. Он никогда не вызывает ошибку и значение по умолчанию.<br /><br /> Соответствующий [ключевое слово наследования](../../cpp/inheritance-keywords.md) и аргумент для [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) — **virtual_inheritance**.<br /><br /> Этот параметр требует более крупные указатели и дополнительный код для интерпретации указателя сравнению с другими параметрами.|  
  
 При указании одного из этих параметров модели наследования, эта модель используется для всех указателей на члены класса, независимо от их типа наследования или объявлен ли указатель до или после класса. Таким образом, если всегда использовать классы с одиночным наследованием, можно уменьшить объем кода при компиляции с **/vms**; тем не менее, если вы хотите использовать наиболее общий случай (за счет максимально возможное представление данных), компиляция с **/vmv**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [/ vmb, / vmg (метод представления)](../../build/reference/vmb-vmg-representation-method.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)