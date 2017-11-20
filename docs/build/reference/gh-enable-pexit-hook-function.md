---
title: "-GH (включить функцию обработчик _pexit) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _pexit
dev_langs: C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 620019d8a286fff472d6f4136bae3046556b367a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (включить функцию-обработчик _pexit)
Вызовы `_pexit` функции в конце каждого метода или функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GH  
```  
  
## <a name="remarks"></a>Примечания  
 `_pexit` Функция не является частью ни одну библиотеку типа, вы должны указать определение для `_pexit`.  
  
 Если не планируется явным образом вызвать `_pexit`, необходимо предоставлять прототип. Функция должна выглядеть, как если бы она имела следующий прототип, и он должен принудительно содержимое регистров на запись и pop без изменения содержимого при выходе:  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit`Аналогично `_penter`;. в разделе [/Gh (включить _penter функция-ловушка)](../../build/reference/gh-enable-penter-hook-function.md) пример создания `_pexit` функции.  
  
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