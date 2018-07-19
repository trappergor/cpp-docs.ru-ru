---
title: Предупреждение (уровень 4) C4220 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4220
dev_langs:
- C++
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5a48bc836bbead8bc9004f797855fcc4c1baaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294171"
---
# <a name="compiler-warning-level-4-c4220"></a>Предупреждение компилятора (уровень 4) C4220
varargs соответствует оставшимся параметрам  
  
 При использовании расширений Майкрософт по умолчанию (/Ze) указатель на функцию соответствует указатель на функцию с аналогичными, но переменными, аргументы.  
  
## <a name="example"></a>Пример  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Такие указатели не совпадают в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).