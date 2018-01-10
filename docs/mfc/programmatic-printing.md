---
title: "Программная печать | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], active documents
- active documents [MFC], printing
- printing [MFC], programmatic
- IPrint interface
- printing [MFC]
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 927a5d9b4bea41157c8cfac6f3dbfe42fc323bb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="programmatic-printing"></a>Программная печать
OLE предоставленный средства для уникальной идентификации постоянных документов (**GetClassFile**) и загрузить их в их связан код (`CoCreateInstance`, **QueryInterface(IID_IPersistFile)**, **QueryInterface(IID_IPersistStorage)**, **IPersistFile::Load**, и **IPersistStorage::Load**). Чтобы дополнительно включить печать документов, вложение активного документа (с использованием существующей схемы OLE не входит в состав OLE 2.0 первоначально) представлен интерфейс печати standard базы, `IPrint`, которые обычно доступны через любой объект, который можно загрузить постоянное состояние типа документа. Каждое представление активного документа можно при необходимости поддерживать **IPrint** интерфейс для предоставления этих возможностей.  
  
 `IPrint` Интерфейс определяется следующим образом:  
  
```  
interface IPrint : IUnknown  
    {  
    HRESULT SetInitialPageNum([in] LONG nFirstPage);  
    HRESULT GetPageInfo(  
        [out] LONG *pnFirstPage,  
        [out] LONG *pcPages);  
    HRESULT Print(  
        [in] DWORD grfFlags,  
        [in,out] DVTARGETDEVICE **pptd,  
        [in,out] PAGESET ** ppPageSet,  
        [in,out] STGMEDIUM **ppstgmOptions,  
        [in] IContinueCallback* pCallback,  
        [in] LONG nFirstPage,  
        [out] LONG *pcPagesPrinted,  
        [out] LONG *pnPageLast);  
    };  
```  
  
 Клиенты и контейнеры просто использовать **IPrint::Print** для указания документа для печати сам после загрузки этого документа, задание печати управляющих флагов, целевое устройство, страниц и дополнительные параметры. Клиент также может управлять продолжение печати через интерфейс `IContinueCallback` (см. ниже).  
  
 Кроме того **IPrint::SetInitialPageNum** поддерживает возможность напечатано, нумерация страниц без проблем, очевидно, что как преимущество для контейнеры активных документов, таких как Office Binder серии документов. **IPrint::GetPageInfo** делает отображение простой информацию разбиения на страницы, позволяя вызывающему объекту получить начальной страницы число, передаваемое ранее **SetInitialPageNum** (или внутренний документа по умолчанию Начальный номер страницы) и число страниц в документе.  
  
 Объекты, поддерживающие `IPrint` помечаются в реестре с возможностью печати для «состояния» ключ, хранящийся в разделе CLSID объекта:  
  
 HKEY_CLASSES_ROOT\CLSID\\{...} \Printable  
  
 `IPrint`обычно реализуется на тот же объект, который поддерживает либо `IPersistFile` или `IPersistStorage`. Возможность программная печать постоянное состояние некоторого класса путем поиска в реестре для ключа «Возможностью печати для состояния» Обратите внимание, вызывающие объекты. В настоящее время «Печатным» указывает на поддержку по крайней мере `IPrint`; другие интерфейсы могут быть определены в будущем которого будут доступны через `QueryInterface` где **IPrint** просто представляет базовый уровень поддержки.  
  
 Во время печати процедуру может понадобиться клиента или контейнер, который инициировал печати для управления ли продолжать печать. Например контейнер может поддерживать команду «Остановить печать», следует как можно быстрее завершить задание печати. Для поддержки этой возможности, клиент печати объекта можно реализовать объект приемника на небольших уведомления с помощью интерфейса `IContinueCallback`:  
  
```  
interface IContinueCallback : IUnknown  
    {  
    HRESULT FContinue(void);  
    HRESULT FContinuePrinting(  
        [in] LONG cPagesPrinted,  
        [in] LONG nCurrentPage,  
        [in] LPOLESTR pszPrintStatus);  
    };  
```  
  
 Этот интерфейс предназначен для использования как функцию обратного вызова универсального продолжения, которая заменяет собой различные процедуры продолжения в API-Интерфейсе Win32 (таких как **AbortProc** для печати и  **EnumMetafileProc** для перечисления метафайл). Таким образом этот интерфейс является полезным в самых разнообразных длительных процессов.  
  
 В случаях, более универсальными **IContinueCallback::FContinue** функция периодически любым процессом длительное время. Возвращает объект приемника `S_OK` для продолжения операции, и **S_FALSE** для остановки в процедуре как можно быстрее.  
  
 **FContinue**, однако не используется в контексте **IPrint::Print**; а печати использует **IContinueCallback::FContinuePrint**. Любой объект печати должен периодически вызывать **FContinuePrinting** передачи число страниц, которые печати, номер страницы, вывод на печать, а также дополнительная строка, описывающая состояние печати, клиент может Выберите для отображения пользователю (например, «страница 5 19)».  
  
## <a name="see-also"></a>См. также  
 [Контейнеры активных документов](../mfc/active-document-containers.md)

