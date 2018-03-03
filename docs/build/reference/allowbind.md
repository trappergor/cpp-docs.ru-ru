---
title: "-ALLOWBIND | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4cbd5c619b0a9e146adb9a8ec9117f59e01b89d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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