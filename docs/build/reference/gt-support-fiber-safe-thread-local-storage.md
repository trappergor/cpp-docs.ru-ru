---
title: -GT (поддержка локальной памяти безопасную относительно волокон) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs:
- C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 493199cf4d5e66a866fbaa87aafc4098c3114cf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373833"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (поддержка локальной памяти потока, безопасной относительно волокон)
Поддерживает безопасность относительно волокон для данных, размещаемых с помощью статических локальной памяти потока, то есть данных, размещаемых с `__declspec(thread)`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GT  
```  
  
## <a name="remarks"></a>Примечания  
 Данные объявлен с `__declspec(thread)` осуществляется с помощью массива локальное хранилище потока (TLS). Массив TLS — это массив адресов, поддерживаемый системой для каждого потока. Каждый адрес в этом массиве предоставляет расположение локальной памяти потока данных.  
  
 Волокно представляет упрощенный объект, который состоит из стека и контекста регистров и могут быть назначены на разные потоки. Волокно может выполняться в любом потоке. Так как волокно может быть выведено из и перезапустить позже в другом потоке, адрес массива TLS не должен упреждающе кэшированы или оптимизированы как общее подвыражение во время вызова функции (см. [/Og (виды глобальной оптимизации)](../../build/reference/og-global-optimizations.md) для параметра сведения о). **/GT** предотвращает подобные оптимизации.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **оптимизации** страницу свойств.  
  
4.  Изменить **включить безопасную относительно волокон оптимизацию** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)