---
title: "Создание объекта ATL Noncreatable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 9ee276d86478bb4a7b6c9839378183bfd49533d6
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="making-an-atl-object-noncreatable"></a>Делая Noncreatable объекта ATL
Атрибуты на основе ATL COM-объекта можно изменить, чтобы клиент не может напрямую создать объект. В этом случае объект будет возвращенные с помощью вызова метода для другого объекта, а не создан напрямую.  
  
### <a name="to-make-an-object-noncreatable"></a>Чтобы сделать объект noncreatable  
  
1.  Удалить [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) для объекта. Если требуется, чтобы этот объект может быть noncreatable, но элемент управления для регистрации, замените OBJECT_ENTRY_AUTO с [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).  
  
2.  Добавить [noncreatable](../../windows/noncreatable.md) атрибут компонентного класса в IDL-файл. Пример:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)


