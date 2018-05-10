---
title: С помощью лямбда-выражений, объектов функций и ограниченных функций | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3e5ab742335cfd6bb47a5105995d7339c7c36a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Использование лямбда-выражений, объектов функций и ограниченных функций
Код C++ AMP, который будет выполняться на сочетания клавиш заданное в качестве аргумента в вызове [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод. Лямбда-выражение или объект функции (функтор) можно предоставить в качестве этого аргумента. Кроме того лямбда-выражения выражение или объект функции может вызвать функцию ограничения C++ AMP. В этом разделе используется алгоритм Добавление массива для демонстрации лямбда-выражений, объектов функций и ограниченных функций. В следующем примере показано алгоритм без кода C++ AMP. Создаются два одномерные массивы одинаковой длины. Соответствующие элементы целое складываются и сохраняются в третьем одномерным массивом. C++ AMP не используется.  
  
```cpp  
void CpuMethod() {  
 
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
 
    for (int idx = 0; idx <5; idx++)  
 {  
    sumCPP[idx] = aCPP[idx] + bCPP[idx];  
 }  
 
    for (int idx = 0; idx <5; idx++)  
 {  
    std::cout <<sumCPP[idx] <<"\n";  
 }  
}  
 
```  
  
## <a name="lambda-expression"></a>Лямбда-выражения  
 С помощью лямбда-выражение — самый прямой способ использования C++ AMP для переработки кода.  
  
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
 });

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  
  
 Лямбда-выражение должно включать один параметр индексирования и должен включать `restrict(amp)`. В примере [array_view](../../parallel/amp/reference/array-view-class.md) `sum` объект имеет ранг 1. Таким образом, параметр инструкции лямбда-выражения, [индекс](../../parallel/amp/reference/index-class.md) объект, который имеет ранг 1. Во время выполнения, лямбда-выражение выполняется один раз для каждого элемента в [array_view](../../parallel/amp/reference/array-view-class.md) объекта. Дополнительные сведения см. в разделе [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).  
  
## <a name="function-object"></a>Объект Function  
 В объект функции, можно выделить код сочетаний клавиш.  
  
```cpp  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
    const array_view<int, 1>& b,  
    const array_view<int, 1>& sum)  
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
    AdditionFunctionObject(a, b, sum));

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  

 Объект функции должен включать конструктор и должен включать перегруженный оператор вызова функции. Оператор вызова функции должен включать один параметр индексирования. Экземпляр объекта функции передается в качестве второго аргумента [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод. В этом примере три [array_view](../../parallel/amp/reference/array-view-class.md) объекты передаются в конструктор объекта функции. [Array_view](../../parallel/amp/reference/array-view-class.md) объект `sum` имеет ранг 1. Таким образом, параметр оператор вызова функции, [индекс](../../parallel/amp/reference/index-class.md) объект, который имеет ранг 1. Во время выполнения, функция выполняется один раз для каждого элемента в [array_view](../../parallel/amp/reference/array-view-class.md) объекта. Дополнительные сведения см. в разделе [вызов функции](../../cpp/function-call-cpp.md) и [объектов функций в стандартной библиотеке C++](../../standard-library/function-objects-in-the-stl.md).  
  
## <a name="c-amp-restricted-function"></a>Функции C++ со спецификатором ограничения AMP  
 Дополнительно, можно выделить код сочетаний клавиш, создав ограниченные функции и вызов его из лямбда-выражения или объекта функции. В следующем примере кода показано, как вызывать только функцию из лямбда-выражения.  
  
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

 });

 
    for (int i = 0; i <5; i++) {  
    std::cout <<sum[i] <<"\n";  
 }  
}  
 
```  
  
 Необходимо включить функцию ограниченных `restrict(amp)` и ограничений, которые описаны в [ограничения (C++ AMP)](../../cpp/restrict-cpp-amp.md).  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)   
 [Вызов функции](../../cpp/function-call-cpp.md)   
 [Объекты функций в стандартной библиотеке C++](../../standard-library/function-objects-in-the-stl.md)   
 [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

