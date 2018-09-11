---
title: -vd (отключение смещений при выполнении конструктора) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vd
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e983da4521db077235c2b879e0d1277b9505e94
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605872"
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
 Позволяет создавать элементы смещения конструктора или деструктора скрытые vtordisp. Этот вариант используется по умолчанию.  
  
 `2`  
 Позволяет использовать [оператор dynamic_cast](../../cpp/dynamic-cast-operator.md) на создаваемого объекта. Например приведение dynamic_cast из виртуального базового класса в производном классе.  
  
 **/ vd2** добавляет поля vtordisp в том случае, если у вас есть виртуальный базовый класс с виртуальными функциями. **/ vd1** должно быть достаточно. Самый распространенный случай, когда **/vd2** необходим при только виртуальную функцию в виртуальном базовом деструктор.  
  
## <a name="remarks"></a>Примечания  
 Эти параметры применяются только для кода C++, используются виртуальные базовые классы.  
  
 Visual C++ реализует поддержку смещения построения C++ в ситуациях, где используется виртуальное наследование. Смещений при выполнении конструктора решают проблему, возникающую, когда виртуальная функция, объявленному в виртуальном базовом и переопределении в производном классе, вызывается из конструктора во время построения дальнейшей производного класса.  
  
 Проблема в том, что виртуальная функция может быть передан неверный `this` указатель в результате несоответствий между смещениями виртуальной базы класса и смещениями его производных классов. Это решение предоставляет смещения одиночное коррекции, называемое полем vtordisp для каждого виртуального базового класса.  
  
 По умолчанию поля vtordisp вводятся всякий раз, когда код определяет пользовательские конструкторы и деструкторы, а также переопределяет виртуальные функции виртуальных базовых классов.  
  
 Эти параметры влияют на все исходные файлы. Используйте [vtordisp](../../preprocessor/vtordisp.md) Чтобы отключить и повторно включить Добавление полей vtordisp по принципу класс.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)