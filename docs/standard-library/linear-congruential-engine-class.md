---
title: Класс linear_congruential_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::linear_congruential_engine
helpviewer_keywords:
- linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
ms.openlocfilehash: 41ce5590476a8327c9449ece5e3173146a04760f
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449893"
---
# <a name="linearcongruentialengine-class"></a>Класс linear_congruential_engine

Создает случайную последовательность, используя линейный конгруэнтный алгоритм.

## <a name="syntax"></a>Синтаксис

```cpp
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

### <a name="parameters"></a>Параметры

*UIntType*<br/>
Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*A*<br/>
**Множитель**. **Предусловие**: См. раздел "Примечания".

*C*<br/>
**Приращение**. **Предусловие**: См. раздел "Примечания".

*M*<br/>
**Остаток от деления**. **Предусловие**: См. в разделе "Примечания".

## <a name="members"></a>Участники

||||
|-|-|-|
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|

`default_seed` — это член-константа, определенный как `1u` и используемый как значение по умолчанию для параметра `linear_congruential_engine::seed` и конструктор с одним значением.

Дополнительные сведения о членах механизма см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Класс шаблона `linear_congruential_engine` — это самый простой механизм генератора, но не самый быстрый или качественный. Улучшением этого механизма является [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md). Ни один из этих механизмов не обеспечивает такую же скорость и качество результатов, как [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Этот механизм формирует значения указанного пользователем беззнакового целого типа, используя рекуррентное соотношение (*period*) `x(i) = (A * x(i-1) + C) mod M`.

Если *M* равно нулю, значение, используемое для операции модуля является `numeric_limits<result_type>::max() + 1`. Последним возвращается состояние механизма или начальное значение, если функция `operator()` не вызывалась.

Если *M* не равно 0, значения аргументов шаблона *объект* и *C* должно быть меньше, чем *M*.

Хотя можно создать генератор на основе этого механизма напрямую, также можно использовать одно из этих предварительно заданных определений типов.

`minstd_rand0`: Минимальный стандартный механизм 1988 (Льюис, Гудмэн и Миллер, 1969).

```cpp
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;
```

`minstd_rand`: Обновленный минимальный стандартный механизм `minstd_rand0` (Парк, Миллер и Стокмайер, 1993).

```cpp
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;
```

Подробные сведения о линейном конгруэнтном алгоритме см. в статье Википедии [Линейный конгруэнтный генератор](https://go.microsoft.com/fwlink/p/?linkid=402446).

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
