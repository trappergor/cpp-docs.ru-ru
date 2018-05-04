---
title: -GR (предоставление информации о типах времени выполнения) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e91f11fa6397d2ba8279998726249182c541d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Предоставление информации о типах во время выполнения)
Добавление кода для проверки типов объектов во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GR[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Когда **/GR** включен, компилятор определяет `_CPPRTTI` макрос препроцессора. По умолчанию **/GR** включен. **Полиморфическом** отключает сведений о типах во время выполнения.  
  
 Используйте **/GR** если компилятору не удается разрешить тип объекта в коде статически. Обычно требуется **/GR** при использовании в коде параметр [оператор dynamic_cast](../../cpp/dynamic-cast-operator.md) или [typeid](../../cpp/typeid-operator.md). Тем не менее **/GR** увеличивает размер разделов .rdata изображения. Если код не использует **dynamic_cast** или **typeid**, **полиморфическом** может привести к созданию изображения меньшего размера.  
  
 Дополнительные сведения о проверке типов во время выполнения см. в разделе [информацию о типах времени выполнения](../../cpp/run-time-type-information.md) в *Справочник по языку C++*.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **языка** страницу свойств.  
  
4.  Изменить **включить сведения о типе времени выполнения** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)