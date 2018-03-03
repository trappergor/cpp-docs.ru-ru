---
title: "-Zc: auto (выведение типа переменной) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd2f0ff353e1243685c94da0c28f29e810b2a9ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (выведение типа переменной)
**/Zc: auto [-]** параметр компилятора сообщает компилятору, как использовать [ключевое слово auto](../../cpp/auto-keyword.md) для объявления переменных. Если указан параметр по умолчанию — **/Zc: auto**, компилятор выводит тип объявленной переменной из выражения инициализации. При указании **/Zc:auto-**, компилятор выделяет переменную для автоматического класса хранения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:auto[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Стандарт языка C++ определяет первоначальное и измененное значение ключевого слова `auto`. Прежде чем [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], ключевое слово объявляло переменную в автоматическом классе хранения; то есть, то есть переменную с локальным временем существования. Начиная с [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], ключевое слово выводит тип переменной из выражения инициализации объявления. Используйте **/Zc: auto [-]** компилятора параметр, чтобы компилятор использовал значение исходный или измененный `auto` ключевое слово.  
  
 Компилятор выдает соответствующее диагностическое сообщение, если применение ключевого слова `auto` противоречит текущему параметру компилятора. Дополнительные сведения см. в разделе [ключевое слово auto](../../cpp/auto-keyword.md). Дополнительные сведения о вопросах соответствия в Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **свойства конфигурации** узла.  
  
3.  Нажмите кнопку **C/C++** узла.  
  
4.  Нажмите кнопку **командной строки** узла.  
  
5.  Добавить **/Zc: auto** или **/Zc:auto-** для **Дополнительные параметры:** области.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)   
 [Ключевое слово auto](../../cpp/auto-keyword.md)