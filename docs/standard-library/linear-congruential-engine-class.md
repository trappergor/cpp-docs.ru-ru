---
title: "Класс linear_congruential_engine | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- linear_congruential_engine
- random/std::linear_congruential_engine
dev_langs:
- C++
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: bbb733e102af57627c00006816bb8d955877d0f8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="linearcongruentialengine-class"></a>Класс linear_congruential_engine
Создает случайную последовательность, используя линейный конгруэнтный алгоритм.  
  
## <a name="syntax"></a>Синтаксис  
```  
class linear_congruential_engine{  
   public:  // types  
   typedef UIntType result_type;  
   // engine characteristics  
   static constexpr result_type multiplier = a;  
   static constexpr result_type increment = c;  
   static constexpr result_type modulus = m;  
   static constexpr result_type min() { return c == 0u  1u: 0u; }  
   static constexpr result_type max() { return m - 1u; }  
   static constexpr result_type default_seed = 1u;  
   // constructors and seeding functions  
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>  
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>  
   void seed(Sseq& q);
   // generating functions  
   result_type operator()();
   void discard(unsigned long long z);
   };  
```  
#### <a name="parameters"></a>Параметры  
 `UIntType`  
 Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
 `A`  
 **Множитель**. **Предварительные условия** : см. раздел "Примечания".  
  
 `C`  
 **Приращение**. **Предварительные условия** : см. раздел "Примечания".  
  
 `M`  
 **Остаток от деления**. **Предварительные условия** : см. раздел "Примечания".  
  
## <a name="members"></a>Члены  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` — это член-константа, определенный как `1u` и используемый как значение по умолчанию для параметра `linear_congruential_engine::seed` и конструктор с одним значением.  
  
 Дополнительные сведения о членах механизма см. в разделе [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона `linear_congruential_engine` — это самый простой механизм генератора, но не самый быстрый или качественный. Улучшением этого механизма является [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Ни один из этих механизмов не обеспечивает такую же скорость и качество результатов, как [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Этот механизм формирует значения указанного пользователем беззнакового целого типа, используя рекуррентное соотношение (*period*) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Если значение `M` равно 0, для операции модуля используется значение `numeric_limits<result_type>::max() + 1`. Последним возвращается состояние механизма или начальное значение, если функция `operator()` не вызывалась.  
  
 Если значение `M` не равно 0, значения аргументов шаблона `A` и `C` должны быть меньше `M`.  
  
 Хотя можно создать генератор на основе этого механизма напрямую, также можно использовать одно из этих предварительно заданных определений типов.  
  
 `minstd_rand0`: Минимальный стандартный механизм 1988 (Льюис, Гудман и Миллер, 1969).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: Обновленный минимальный стандартный механизм `minstd_rand0` (Парк, Миллер и Стокмайер, 1993).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Подробные сведения о линейном конгруэнтном алгоритме см. в статье Википедии [Линейный конгруэнтный генератор](http://go.microsoft.com/fwlink/LinkId=402446).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<random>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<random>](../standard-library/random.md)



