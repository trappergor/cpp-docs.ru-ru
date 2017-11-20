---
title: "-vd (отключение смещений при выполнении конструктора) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /vd
dev_langs: C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c06c67142e3e0af4582292304ff2eee8445e014
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="vd-disable-construction-displacements"></a>/vd (отключение смещений при выполнении конструктора)
## <a name="syntax"></a>Синтаксис  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>Аргументы  
 `0`  
 Подавляет члена смещения конструктора или деструктора vtordisp. Выберите этот параметр только в том случае, если вы уверены, что все конструкторы и деструкторы классов вызывают виртуальные функции виртуально.  
  
 `1`  
 Позволяет создавать скрытые vtordisp-члены смещения конструктора или деструктора. Этот вариант используется по умолчанию.  
  
 `2`  
 Позволяет использовать [оператор dynamic_cast](../../cpp/dynamic-cast-operator.md) , создаваемого объекта. Например, приведение dynamic_cast из виртуального базового класса в производный класс.  
  
 **/ vd2** добавляет поле vtordisp при наличии виртуальный базовый класс с виртуальными функциями. **/ vd1** должно быть достаточно. Наиболее распространенной случай, когда **/vd2** необходим при только виртуальные функции в виртуальном базовом деструктор.  
  
## <a name="remarks"></a>Примечания  
 Эти параметры применяются только для кода C++, используются виртуальные базовые классы.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]реализует поддержку смещения построения C++ в ситуациях, где используется виртуальное наследование. Смещений решить проблему, возникающую, когда виртуальная функция, объявленному в виртуальном базовом и переопределения в производном классе, вызывается из конструктора во время построения дальнейшей производного класса.  
  
 Проблема заключается в том, что виртуальная функция может быть передан неправильный `this` указателя в результате несоответствия между смещениями виртуальной базы класса и смещениями его производных классов. Это решение предоставляет смещения одиночное коррекции, называемое полем vtordisp для каждого виртуального базового класса.  
  
 По умолчанию поля vtordisp вводятся всякий раз, когда в коде определяется пользовательские конструкторы и деструкторы, а также переопределяются виртуальные функции виртуальных базовых классов.  
  
 Эти параметры влияют на все исходные файлы. Используйте [vtordisp](../../preprocessor/vtordisp.md) Чтобы отключить и повторно включить поля vtordisp на основе класс.  
  
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