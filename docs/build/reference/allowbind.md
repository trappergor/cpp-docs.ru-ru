---
title: -ALLOWBIND | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af4a9f3d898d0087f0e8e861ccfe72e4adadb1de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="allowbind"></a>/ALLOWBIND
Указывает, можно ли привязать библиотеку DLL.  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 **/ALLOWBIND** параметр задает бит в заголовке DLL, указывающих Bind.exe допустимости для привязки изображения. Привязки можно разрешить изображения загружаются быстрее, если загрузчик не rebase и выполнить адресную привязку для каждой библиотеки DLL, на которую указывает ссылка. Может потребоваться не библиотеку DLL, если он имеет цифровую подпись — подпись недействительной привязки. Привязка имеет смысл, если технология address space макета randomization (ASLR) включен для образа с помощью **/DYNAMICBASE** в версиях Windows, который поддерживает Технологию.  
  
 Используйте **/ALLOWBIND:NO** для предотвращения Bind.exe привязка библиотеки DLL.  
  
 Дополнительные сведения см. в разделе [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) компоновщика.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)