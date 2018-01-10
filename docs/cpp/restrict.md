---
title: "ограничить | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: restrict_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24fa0dae15fb0d4dfab8d481c6626c7611295572
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="restrict"></a>restrict
**Блок, относящийся только к системам Microsoft**  
  
 Применяется к объявлению или определению функции, возвращающей тип указателя; сообщает компилятору, что функция возвращает объект, который не будет связываться ни с какими другими указателями.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>Примечания  
 Компилятор распространяет `__declspec(restrict)`. Например, функция среды CRT `malloc` декорируется модификатором `__declspec(restrict)`; поэтому подразумевается, что указатели, инициализированные в расположениях памяти с помощью функции `malloc`, также не будут иметь псевдонимов.  
  
 Компилятор не проверяет, действительно ли указатель не имеет псевдонимов. Разработчик должен обеспечить, чтобы программа не создавала псевдонимы для указателя, помеченного модификатором `restrict __declspec`.  
  
 Похожую семантику с переменными в разделе [__restrict](../cpp/extension-restrict.md).  
  
## <a name="example"></a>Пример  
 В разделе [noalias](../cpp/noalias.md) пример использования `restrict`.  
  
 Сведения о ключевом слове ограничение, который является частью C++ AMP. в разделе [ограничение (C++ AMP)](../cpp/restrict-cpp-amp.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)