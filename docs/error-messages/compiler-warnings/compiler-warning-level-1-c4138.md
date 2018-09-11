---
title: Предупреждение компилятора (уровень 1) C4138 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc3102f18021c16663bdf61dcde6df5e6893d46c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197092"
---
# <a name="compiler-warning-level-1-c4138"></a>Предупреждение компилятора (уровень 1) C4138
"*/" найден вне комментария  
  
 Закрывающему разделителю комментария не предшествует разделитель, открывающий комментарий. Компилятор предполагает пробел между звездочкой (<strong>\*</strong>) и косую черту (/).  
  
## <a name="example"></a>Пример  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 Это предупреждение может быть вызвано попыткой создать вложенный комментарий.  
  
 Чтобы устранить это предупреждение, раскомментируйте код, содержащий комментарии, поместите его в блок **#if/#endif** и задайте для управляющего выражения значение нуль:  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```