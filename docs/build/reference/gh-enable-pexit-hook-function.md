---
title: -GH (включить функцию обработчик _pexit) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e11c27af36eb539b22f3833a73341ff3065e97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374509"
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
  
 `_pexit` Аналогично `_penter`;. в разделе [/Gh (включить _penter функция-ловушка)](../../build/reference/gh-enable-penter-hook-function.md) пример создания `_pexit` функции.  
  
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