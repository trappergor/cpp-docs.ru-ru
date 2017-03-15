---
title: "threadprivate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2f5d64c172cac629a80cdf4a1057afbbf9789f5f
ms.lasthandoff: 02/24/2017

---
# <a name="threadprivate"></a>threadprivate
Указывает, что переменная закрытого потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Разделенный запятыми список переменных, которые вы хотите сделать закрытым для потока. `var`необходимо глобальных или имен уровня переменной или статической локальной переменной.  
  
## <a name="remarks"></a>Примечания  
 `threadprivate` Директива поддерживает без предложения OpenMP.  
  
 Дополнительные сведения см. в разделе [2.7.1 директива threadprivate](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 `threadprivate` На основе директива [поток](../../../cpp/thread.md) `__declspec` атрибут; ограничения на **__declspec(thread)** применяются к `threadprivate`.  
  
 Нельзя использовать `threadprivate` в любой библиотекой DLL, которые будут загружены через [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Сюда входят библиотеки DLL, загружаемые с [/DELAYLOAD (загрузка импорта с задержкой)](../../../build/reference/delayload-delay-load-import.md), который также используется **LoadLibrary**.  
  
 Можно использовать `threadprivate` в библиотеке DLL, статически загружается при запуске процесса.  
  
 Поскольку `threadprivate` на основе **__declspec(thread)**, `threadprivate` переменной будет существовать в любом потоке в процессе работы не только потоки, которые являются частью группы потоков, порожденном параллельной области.  Это деталь реализации, который может иметь в виду, так как вы могли заметить, например, конструкторы для `threadprivate` определяемого пользователем типа вызывается дополнительные чаще, чем ожидалось.  
  
 A `threadprivate` переменной типа destructable не обязательно иметь его деструктор вызывается.  Например:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Пользователи не имеют контроля о том, когда потоки, образующей параллельной области будет завершена.  Если при завершении процесса, потоки не будут получать уведомления о выходе процесса и деструктор не будет вызван для существует этих потоков `threaded_var` в любом потоке, за исключением того, который завершает работу (в данном случае — основной поток).  Поэтому код не следует рассчитывать на правильное уничтожение `threadprivate` переменных.  
  
## <a name="example"></a>Пример  
 Пример использования `threadprivate`, в разделе [частного](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)
