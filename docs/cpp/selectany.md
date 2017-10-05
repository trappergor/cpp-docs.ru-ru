---
title: "selectany | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- selectany_cpp
- selectany
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9c17221e2d0875505d9aa3f1132ea4a4b6d4c489
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="selectany"></a>selectany
**Блок, относящийся только к системам Майкрософт**  
  
 Сообщает компилятору, что объявленный элемент глобальных данных (переменная или объект) является универсальным COMDAT (упакованной функцией).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec( selectany ) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 Во время компоновки, если отображается несколько определений COMDAT, компоновщик выбирает один из них и игнорирует остальные. Если параметр компоновщика [/OPT: ref](../build/reference/opt-optimizations.md) (оптимизации) установлен, то будет возникать исключение COMDAT для удаления всех элементов данных без ссылок в выходных данных компоновщика.  
  
 Конструкторы и назначение с помощью глобальной функции или статических методов в объявлении не создадут ссылку и не предотвратят исключение /OPT:REF. Побочные эффекты такого кода не должны быть зависимыми, если не существует других ссылок на данные.  
  
 Для динамически инициализированных глобальных объектов `selectany` также удалит код инициализации объекта без ссылки.  
  
 Обычно элемент глобальных данных можно инициализировать только один раз в проекте EXE или DLL. `selectany` можно использовать при инициализации глобальных данных, определенных в заголовках, если одинаковый заголовок отображается в нескольких исходных файлах. `selectany` доступен в обоих компиляторах: C и C++.  
  
> [!NOTE]
>  `selectany` можно применить только к существующей инициализации элементов глобальных данных, видимых извне.  
  
## <a name="example"></a>Пример  
 В следующем коде демонстрируется использование атрибута `selectany`.  
  
```  
//Correct - x1 is initialized and externally visible   
__declspec(selectany) int x1=1;  
  
//Incorrect - const is by default static in C++, so   
//x2 is not visible externally (This is OK in C, since  
//const is not by default static in C)  
const __declspec(selectany) int x2 =2;  
  
//Correct - x3 is extern const, so externally visible  
extern const __declspec(selectany) int x3=3;  
  
//Correct - x4 is extern const, so it is externally visible  
extern const int x4;  
const __declspec(selectany) int x4=4;  
  
//Incorrect - __declspec(selectany) is applied to the uninitialized  
//declaration of x5  
extern __declspec(selectany) int x5;  
  
// OK: dynamic initialization of global object  
class X {  
public:  
X(int i){i++;};  
int i;  
};  
  
__declspec(selectany) X x(1);  
```  
  
## <a name="example"></a>Пример  
 Этот код показывает, как использовать `selectany` атрибут, чтобы включить свертывание записей COMDAT при использовании [/OPT: ICF](../build/reference/opt-optimizations.md) компоновщика. Обратите внимание, что данные должны быть отмечены `selectany` и помещается в **const** раздел (только для чтения). Раздел, доступный только для чтения, необходимо указать явно.  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
