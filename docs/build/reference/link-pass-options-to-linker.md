---
title: "-связь (Pass параметров компоновщику) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /link
dev_langs: C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e2a193ff5f1e76d4e7ceb160325c1e748634c3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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