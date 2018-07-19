---
title: Определения и объявления в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d44a98fee82e41252b27fa5a1605b04a15af9115
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383489"
---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C)
**Блок, относящийся только к системам Microsoft**  
  
 Интерфейс DLL относится ко всем элементам (функциям и данным), про которые известно, что некоторая программа в системе будет их экспортировать, т. е. ко всем элементам, объявленным как **dllimport** или `dllexport`. Во всех объявлениях, включенных в интерфейс DLL, нужно указать атрибут **dllimport** или `dllexport`. Однако определение может задавать только атрибут `dllexport`. Например, следующее определение функции вызовет ошибку компилятора.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int func()    /* Error; dllimport prohibited in */  
                        /* definition. */  
{  
   return 1;  
}  
```  
  
 Показанный ниже код также вызовет ошибку.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int i = 10;      /* Error; this is a definition. */  
```  
  
 Однако следующий синтаксис правильный.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport int i = 10;      /* Okay: this is an export definition. */  
```  
  
 Использование атрибута `dllexport` подразумевает определение, а **dllimport** — объявление. Для обеспечения объявления ключевое слово `extern` следует использовать с аргументом `dllexport`; в противном случае подразумевается определение.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k;   /* These are correct and imply */  
Dllimport int j;          /* a declaration. */      
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функции импорта и экспорта DLL](../c-language/dll-import-and-export-functions.md)