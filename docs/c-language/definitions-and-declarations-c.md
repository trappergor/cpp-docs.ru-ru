---
title: "Определения и объявления в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e6523addc4ad4403c3dd74b5101081178b3ed2ec
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C)
**Блок, относящийся только к системам Майкрософт**  
  
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
