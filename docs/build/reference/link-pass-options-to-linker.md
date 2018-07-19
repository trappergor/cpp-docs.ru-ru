---
title: -связь (Pass параметров компоновщику) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /link
dev_langs:
- C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b22e21022162a0f9f75e41e3e0bfdce348947e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373297"
---
# <a name="link-pass-options-to-linker"></a>/link (Передача параметров компоновщику)
Передает компоновщику один или несколько параметров компоновщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/link linkeroptions  
```  
  
## <a name="arguments"></a>Аргументы  
 `linkeroptions`  
 Параметр компоновщика или параметры для передачи в компоновщик.  
  
## <a name="remarks"></a>Примечания  
 **/Link** параметр и его параметры компоновщика должны располагаться после имен файлов и параметров CL. Пробел требуется между **/link** и `linkeroptions`. Дополнительные сведения см. в разделе [параметры компоновщика](../../build/reference/setting-linker-options.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств компоновщика.  
  
4.  Измените одно или несколько свойств.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   Данного параметра компилятора программным способом нельзя.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)