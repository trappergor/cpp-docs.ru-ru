---
title: "Класс Duration | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration
dev_langs:
- C++
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 843e4954b3a5b20d504dd5c8bf582dc56d4cbcbd
ms.lasthandoff: 02/24/2017

---
# <a name="duration-class"></a>Класс duration
Описывает тип, содержащий *интервал времени*, представляющий собой затраченное время между двумя точками времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Rep, class Period = ratio<1>>  
class duration;  
template <class Rep, class Period>  
class duration;  
template <class Rep, class Period1, class Period2>  
class duration <duration<Rep, Period1>, Period2>;  
```  
  
## <a name="remarks"></a>Примечания  
 Аргумент шаблона `Rep` описывает тип, используемый для удержания числа тактов в интервале. Аргумент шаблона `Period` — экземпляр [отношения](../standard-library/ratio.md), описывающий размер интервала, который представляет каждый такт.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|duration::period Typedef|Синоним для параметра-шаблона `Period`.|  
|duration::rep Typedef|Синоним для параметра-шаблона `Rep`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор duration::duration](#duration__duration_constructor)|Создает объект `duration`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[duration::count](#duration__count_method)|Возвращает количество тактов в интервале времени.|  
|[duration::max](#duration__max_method)|Статический. Возвращает максимальное допустимое значение параметра-шаблона `Ref`.|  
|[duration::min](#duration__min_method)|Статический. Возвращает минимально допустимое значение параметра-шаблона `Ref`.|  
|[duration::zero](#duration__zero_method)|Статический. Фактически возвращает `Rep` (0).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[duration::operator-](#duration__operator-)|Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.|  
|[duration::operator--](#duration__operator--)|Уменьшает на единицу накопленный счетчик тактов.|  
|[duration::operator=](#duration__operator_eq)|Уменьшает накопленный счетчик тактов по модулю на указанное значение.|  
|[duration::operator*=](#duration__operator_star_eq)|Умножает накопленный счетчик тактов на указанное значение.|  
|[duration::operator/=](#duration__operator__eq)|Делит накопленный счетчик тактов на счетчик тактов указанного объекта `duration`.|  
|[duration::operator+](#duration__operator_add)|Возвращает `*this`.|  
|[duration::operator++](#duration__operator_add_add)|Увеличивает на единицу накопленный счетчик тактов.|  
|[duration::operator+=](#duration__operator_add_eq)|Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.|  
|[duration::operator-=](#duration__operator-_eq)|Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** chrono  
  
 **Пространство имен:** std::chrono  
  
##  <a name="a-namedurationcountmethoda--durationcount"></a><a name="duration__count_method"></a>  duration::count  
 Получает количество тактов в интервале времени.  
  
```  
constexpr Rep count() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество тактов в интервале времени.  
  
##  <a name="a-namedurationdurationconstructora--durationduration-constructor"></a><a name="duration__duration_constructor"></a> Конструктор duration::duration  
 Создает объект `duration`.  
  
```  
constexpr duration() = default;  
 
template <class Rep2>  
constexpr explicit duration(const Rep2& R);

 
template <class Rep2, class Period2>  
constexpr duration(const duration<Rep2, Period2>& Dur);
```  
  
### <a name="parameters"></a>Параметры  
 `Rep2`  
 Арифметический тип для представления числа тактов.  
  
 `Period2`  
 Специализация шаблона `std::ratio` для представления тактового периода в секундах.  
  
 `R`  
 Количество тактов в периоде по умолчанию.  
  
 `Dur`  
 Количество тактов в периоде, указанном в `Period2`.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию создает объект, который не инициализирован. Инициализация значения с помощью пустых фигурных скобок инициализирует объект, представляющий интервал времени нулевых тактов.  
  
 Второй конструктор (конструктор аргументов шаблона&1;) создает объект, представляющий интервал времени в `R` тактов, используя период по умолчанию `std::ratio<1>`. Чтобы избежать округления значений счетчика тактов, считается ошибкой создание объекта длительности из типа представления `Rep2`, который может рассматриваться как тип с плавающей запятой в то время, когда `duration::rep` не может рассматриваться как тип с плавающей запятой.  
  
 Третий конструктор (конструктор аргументов шаблона&2;) создает объект, представляющий интервал времени, длина которого совпадает с длиной интервала времени, заданного параметром `Dur`. Чтобы избежать усечения значений счетчика тактов, считается ошибкой создание объекта длительности из другого объекта длительности, тип которого *несоизмерим* с целевым типом.  
  
 Тип длительности `D1` *несоизмерим* с другим типом длительности `D2`, если `D2` не может рассматриваться как тип с плавающей запятой, а [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) не равен 1.  
  
 Если `Rep2` неявно не преобразуется в `rep` и `treat_as_floating_point<rep>`*не содержит значение true* или `treat_as_floating_point<Rep2>`*не содержит значение false*, второй конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).  
  
 Если второй конструктор не участвует в разрешении перегрузки и `treat_as_floating_point<rep>`*не содержит значение true* или оба `ratio_divide<Period2, period>::den` не равны 1 и `treat_as_floating_point<Rep2>`*не содержит значение false*, третий конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-namedurationmaxmethoda--durationmax"></a><a name="duration__max_method"></a>  duration::max  
 Статический метод, который возвращает верхнюю границу значений типа параметра-шаблона `Ref`.  
  
```  
static constexpr duration max();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактически возвращает `duration(duration_values<rep>::max())`.  
  
##  <a name="a-namedurationminmethoda--durationmin"></a><a name="duration__min_method"></a>  duration::min  
 Статический метод, который возвращает нижнюю границу значений типа параметра-шаблона `Ref`.  
  
```  
static constexpr duration min();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактически возвращает `duration(duration_values<rep>::min())`.  
  
##  <a name="a-namedurationoperator-a--durationoperator-"></a><a name="duration__operator-"></a>  duration::operator-  
 Возвращает копию объекта `duration` вместе с отрицательным счетчиком тактов.  
  
```  
constexpr duration operator-() const;
```  
  
##  <a name="a-namedurationoperator--a--durationoperator--"></a><a name="duration__operator--"></a>  duration::operator--  
 Уменьшает на единицу накопленный счетчик тактов.  
  
```  
duration& operator--();

duration operator--(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый метод возвращает `*this`.  
  
 Второй метод возвращает копию `*this`, сделанную до уменьшения значения.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator_eq"></a>  duration::operator=  
 Уменьшает накопленный счетчик тактов по модулю на указанное значение.  
  
```  
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Параметры  
 `Div`  
 Для первого метода `Div` представляет счетчик тактов. Для второго метода `Div` — объект `duration`, который содержит счетчик тактов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` после выполнения операции по модулю.  
  
##  <a name="a-namedurationoperatorstareqa--durationoperator"></a><a name="duration__operator_star_eq"></a>  duration::operator*=  
 Умножает накопленный счетчик тактов на указанное значение.  
  
```  
duration& operator*=(const rep& Mult);
```  
  
### <a name="parameters"></a>Параметры  
 `Mult`  
 Значение типа, которое задается параметром `duration::rep`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` после выполнения умножения.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator__eq"></a>  duration::operator/=  
 Делит накопленный счетчик тактов на указанное значение.  
  
```  
duration& operator/=(const rep& Div);
```  
  
### <a name="parameters"></a>Параметры  
 `Div`  
 Значение типа, которое задается параметром `duration::rep`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` после выполнения деления.  
  
##  <a name="a-namedurationoperatoradda--durationoperator"></a><a name="duration__operator_add"></a>  duration::operator+  
 Возвращает `*this`.  
  
```  
constexpr duration operator+() const;
```  
  
##  <a name="a-namedurationoperatoraddadda--durationoperator"></a><a name="duration__operator_add_add"></a>  duration::operator++  
 Увеличивает на единицу накопленный счетчик тактов.  
  
```  
duration& operator++();

duration operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый метод возвращает `*this`.  
  
 Второй метод возвращает копию `*this`, сделанную до увеличения значения.  
  
##  <a name="a-namedurationoperatoraddeqa--durationoperator"></a><a name="duration__operator_add_eq"></a>  duration::operator+=  
 Добавляет счетчик тактов указанного объекта `duration` к накопленному счетчику тактов.  
  
```  
duration& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>Параметры  
 `Dur`  
 Объект `duration`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` после выполнения сложения.  
  
##  <a name="a-namedurationoperator-eqa--durationoperator-"></a><a name="duration__operator-_eq"></a>  duration::operator-=  
 Вычитает счетчик тактов указанного объекта `duration` из накопленного счетчика тактов.  
  
```  
duration& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>Параметры  
 `Dur`  
 Объект `duration`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` после выполнения вычитания.  
  
##  <a name="a-namedurationzeromethoda--durationzero"></a><a name="duration__zero_method"></a>  duration::zero  
 Возвращает `duration(duration_values<rep>::zero())`.  
  
```  
static constexpr duration zero();
```  
  
##  <a name="a-namedurationoperatormodeqa--durationoperator-mod"></a><a name="duration__operator_mod_eq"></a>  duration::operator mod=  
 Уменьшает накопленный счетчик тактов по модулю на Div или Div.count().  
  
```  
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Параметры  
 `Div`  
 Делитель, который является либо объектом длительности, либо значением, представляющим значение счетчика тактов.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член уменьшает накопленный счетчик тактов по модулю на Div и возвращает *this. Вторая функция-член уменьшает накопленный счетчик тактов по модулю на Div.count() и возвращает \*this.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [Структура duration_values](../standard-library/duration-values-structure.md)

