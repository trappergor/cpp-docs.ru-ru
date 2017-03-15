---
title: "Использование лямбда-выражений, объектов функций и ограниченных функций | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Использование лямбда-выражений, объектов функций и ограниченных функций
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Код C\+\+ AMP, который должен выполняться на ускорителе, указывается в качестве аргумента при вызове метода [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).  В качестве этого аргумента можно предоставить или лямбда\-выражение или объект функции \(функтор\).  Кроме того, лямбда\-выражение или объект функции могут вызвать ограниченную функцию C\+\+ AMP.  Этот раздел использует алгоритм сложения массивов для демонстрации лямбда\-выражений, объектов функций и ограниченных функций.  В следующем примере показан алгоритм без кода C\+\+ AMP.  Создаются два одномерных массива одинаковой длины.  Соответствующие элементы целого типа добавляются и хранятся в третьем 1\-мерном массиве.  C\+\+ AMP не используется.  
  
```cpp  
  
void CpuMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
## лямбда\-выражение  
 Применение лямбда\-выражения – самый прямой способ использования C\+\+ AMP с целью переписать код.  
  
```cpp  
  
void AddArraysWithLambda() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Лямбда\-выражение должно включать один параметр индексирования и `restrict(amp)`.  В этом примере объект [array\_view](../../parallel/amp/reference/array-view-class.md) `sum` имеет размерность 1.  Поэтому параметр в лямбда\-выражении – объект [index](../../parallel/amp/reference/index-class.md), имеющий ранг 1.  Во время выполнения лямбда\-выражение выполняется один раз для каждого элемента в объекте [array\_view](../../parallel/amp/reference/array-view-class.md).  Для получения дополнительной информации см. [Синтаксис лямбда\-выражений](../../cpp/lambda-expression-syntax.md).  
  
## Объект Function  
 Можно включить код ускорителя в объекте функции.  
  
```cpp  
  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
        const array_view<int, 1>& b,  
        const array_view<int, 1>& sum  
    )  
    : a(a), b(b), sum(sum)  
    {  
    }  
  
    void operator()(index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
  
private:  
    array_view<int, 1> a;  
    array_view<int, 1> b;  
    array_view<int, 1> sum;  
};  
  
void AddArraysWithFunctionObject() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        AdditionFunctionObject(a, b, sum)  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Объект функции должен содержать конструктор и перегрузку оператора вызова функции.  Оператор вызова функции должен включать один параметр индексирования.  Экземпляр объекта функции передается в качестве второго аргумента методу [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).  В этом примере три объекта [array\_view](../../parallel/amp/reference/array-view-class.md) передаются конструктору объекта функции.  Объект [array\_view](../../parallel/amp/reference/array-view-class.md)`sum` имеет ранг 1.  Поэтому параметр в операторе вызова функции – объект [index](../../parallel/amp/reference/index-class.md), имеющий ранг 1.  Во время выполнения функция выполняется один раз для каждого элемента в объекте [array\_view](../../parallel/amp/reference/array-view-class.md).  Дополнительные сведения см. в разделах [Вызов функции](../Topic/Function%20Call%20\(C++\).md) и [Объекты функций в библиотеке STL](../../standard-library/function-objects-in-the-stl.md).  
  
## Ограниченная функция C\+\+ AMP  
 Можно и дальше факторизовать код ускорителя, создавая ограниченную функцию и вызывая ее из лямбда\-выражения или объекта функции.  В следующем примере кода показано, как вызывать ограниченную функцию из лямбда\-выражения.  
  
```cpp  
  
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            AddElementsWithRestrictedFunction(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Ограниченная функция должна включать `restrict(amp)` и соответствовать ограничениям, описанным в [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md).  
  
## См. также  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Синтаксис лямбда\-выражений](../../cpp/lambda-expression-syntax.md)   
 [Вызов функции](../Topic/Function%20Call%20\(C++\).md)   
 [Объекты функций в библиотеке STL](../../standard-library/function-objects-in-the-stl.md)   
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)