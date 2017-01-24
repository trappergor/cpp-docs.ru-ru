---
title: "Класс linear_congruential_engine | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.linear_congruential_engine"
  - "random/std::tr1::linear_congruential_engine"
  - "linear_congruential_engine"
  - "std::tr1::linear_congruential_engine"
  - "tr1.linear_congruential_engine"
  - "tr1::linear_congruential_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "linear_congruential_engine - класс"
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс linear_congruential_engine
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает случайную последовательность, используя линейный конгруэнтный алгоритм.  
  
## Синтаксис  
  
```  
template<class UIntType, UIntType A, UIntType C, UIntType M>  
class linear_congruential_engine{  
public:  
    // types  
    typedef UIntType result_type;  
  
    // engine characteristics  
    static constexpr result_type multiplier = a;  
    static constexpr result_type increment = c;  
    static constexpr result_type modulus = m;  
    static constexpr result_type min() { return c == 0u ? 1u: 0u; }  
    static constexpr result_type max() { return m - 1u; }  
    static constexpr result_type default_seed = 1u;  
  
    // constructors and seeding functions  
    explicit linear_congruential_engine(result_type s = default_seed);  
    template<class Sseq> explicit linear_congruential_engine(Sseq& q);  
    void seed(result_type s = default_seed);  
    template<class Sseq> void seed(Sseq& q);  
  
    // generating functions  
    result_type operator()();  
    void discard(unsigned long long z);  
};  
```  
  
#### Параметры  
 `UIntType`  
 Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random\>](../standard-library/random.md).  
  
 `A`  
 **Множитель**.**Предусловие**: см. заметки.  
  
 `C`  
 **Инкремент**.**Предусловие**: см. заметки.  
  
 `M`  
 **Модуль**.**Предусловие**: см. заметки.  
  
## Члены  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` — это член\-константа, определенный как `1u` и используемый как значение по умолчанию для параметра `linear_congruential_engine::seed` и конструктор с одним значением.  
  
 Дополнительные сведения о членах механизма см. в разделе [\<random\>](../standard-library/random.md).  
  
## Заметки  
 Класс шаблона `linear_congruential_engine` — это самый простой механизм генератора, но не самый быстрый или качественный. Улучшением этого механизма является [substract\_with\_carry\_engine](../Topic/subtract_with_carry_engine%20Class.md). Ни один из этих механизмов не обеспечивает такую же скорость и качество результатов, как механизм [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Этот механизм формирует значения указанного пользователем беззнакового целого типа, используя рекуррентное соотношение \(*период*\) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Если значение `M` равно 0, для операции модуля используется значение `numeric_limits<result_type>::max() + 1`. Последним возвращается состояние механизма или начальное значение, если функция `operator()` не вызывалась.  
  
 Если значение `M` не равно 0, значения аргументов шаблона `A` и `C` должны быть меньше `M`.  
  
 Несмотря на то, что можно создать генератор на основе этого механизма напрямую, можно использовать один из этих предопределенных определения типов.  
  
 `minstd_rand0`: минимальный стандартный механизм 1988 \(Льюис, Гудмэн и Миллер, 1969\).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: Обновленный минимальный стандартный механизм `minstd_rand0` \(парк, Миллер и Стокмайер, 1993\).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Подробные сведения о линейном конгруэнтном алгоритме см. в статье Википедии [Линейный конгруэнтный генератор](http://go.microsoft.com/fwlink/?LinkId=402446).  
  
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)