---
title: "Класс mersenne_twister_engine | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "random/std::tr1::mersenne_twister_engine"
  - "tr1.mersenne_twister_engine"
  - "std.tr1.mersenne_twister_engine"
  - "std::tr1::mersenne_twister_engine"
  - "tr1::mersenne_twister_engine"
  - "mersenne_twister_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mersenne_twister_engine - класс"
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс mersenne_twister_engine
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает высококачественную последовательность случайных целых чисел на основе алгоритма "Вихрь Мерсенна".  
  
## Синтаксис  
  
```  
template<class UIntType,   
    size_t W, size_t N, size_t M, size_t R,  
    UIntType A, size_t U, UIntType D, size_t S,  
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>  
class mersenne_twister_engine;  
```  
  
#### Параметры  
 `UIntType`  
 Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random\>](../standard-library/random.md).  
  
 `W`  
 **Размер слова**. Размер каждого слова последовательности состояния в битах.**Предусловие**: `2u < W ≤ numeric_limits<UIntType>::digits`  
  
 `N`  
 **Размер состояния**. Количество элементов \(значений\) в последовательности состояний.  
  
 `M`  
 **Размер сдвига**. Число элементов, которые пропускаются при каждом повороте.**Предусловие**: `0 < M ≤ N`  
  
 `R`  
 **Биты маски**.**Предусловие**: `R ≤ W`  
  
 `A`  
 **Маска XOR**.**Предусловие**: `A ≤ (1u<<W) - 1u`  
  
 `U`, `S`, `T`, `L`  
 **Параметры сдвига при смешивании**. Используются как значения сдвига во время шифрования \(смешивания\). Предусловие: `U,S,T,L ≤ W`  
  
 `D`, `B`, `C`  
 **Параметры битовой маски смешивания**. Используются как значения битовой маски во время шифрования \(смешивания\). Предусловие: `D,B,C ≤ (1u<<W) - 1u`  
  
 `F`  
 **Множитель инициализации**. Используется для инициализации последовательности. Предусловие: `F ≤ (1u<<W) - 1u`  
  
## Члены  
  
||||  
|-|-|-|  
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|  
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|  
  
 `default_seed` — это член\-константа, определенный как `5489u` и используемый как значение по умолчанию для параметра `mersenne_twister_engine::seed` и конструктор с одним значением.  
  
 Дополнительные сведения о членах механизма см. в разделе [\<random\>](../standard-library/random.md).  
  
## Заметки  
 Этот класс шаблона описывает механизм случайных чисел, возвращает значения в замкнутом интервале \[`0`, `2`<sup>W</sup> \- `1`\]. Он содержит большое `W * (N - 1) + R`\-разрядное целое значение. Класс извлекает `W` разрядов из этого значения. Когда использованы все разряды, большое значение перемешивается за счет сдвига и смешивания разрядов для получения нового набора разрядов. Состояние механизма является последним `N``W`\-битовые значения, используемые при `operator()` был вызван по крайней мере `N` время, в противном случае `M``W`\-разрядных значений, которые были использованы и последнего `N - M` значений начального значения.  
  
 Генератор перемешивает большое значение, используя генерализованный регистр сдвига, заданный значениями сдвига `N` и `M`, значением поворота `R` и условной XOR\-маской `A`. Кроме того, разряды регистра сдвига шифруются в соответствии с матрицей, заданной значениями `U`, `D`, `S`, `B`, `T`, `C` и `L`.  
  
 Аргумент шаблона `UIntType` должен быть достаточно большим, чтобы хранить значения `2`<sup>W</sup> \- `1`. Значения других аргументов шаблона должны удовлетворять следующим требованиям: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.  
  
 Несмотря на то, что можно создать генератор на основе этого механизма напрямую, рекомендуется использовать один из этих стандартных определений типов:  
  
 `mt19937`: 32\-разрядных вихрь мерсенна \(Матсумото и Нишимура, 1998\).  
  
```  
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,   
    31, 0x9908b0df,   
    11, 0xffffffff,   
    7, 0x9d2c5680,   
    15, 0xefc60000,   
    18, 1812433253> mt19937;  
```  
  
 `mt19937_64`: 64\-разрядный вихрь мерсенна \(Матсумото и Нишимура, 2000\).  
  
```  
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,   
    31, 0xb5026f5aa96619e9ULL,   
    29, 0x5555555555555555ULL,   
    17, 0x71d67fffeda60000ULL,   
    37, 0xfff7eee000000000ULL,   
    43, 6364136223846793005ULL> mt19937_64;  
```  
  
 Подробные сведения об алгоритме вихрь Мерсенна см. в статье Википедии [вихрь мерсенна](http://go.microsoft.com/fwlink/?LinkId=402356).  
  
## Пример  
 Пример кода см. в разделе [\<random\>](../standard-library/random.md).  
  
## Требования  
 **Заголовок:** \<random\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<random\>](../standard-library/random.md)