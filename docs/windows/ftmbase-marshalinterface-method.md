---
title: Метод FtmBase::MarshalInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff0c1a5e41dfe46f2d88aeeb3093dbc9ee4d4005
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570061"
---
# <a name="ftmbasemarshalinterface-method"></a>Метод FtmBase::MarshalInterface
Записывает в поток данные, необходимые для инициализации прокси-объект в какой-либо процесс клиента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *pStm*  
 Указатель на поток, который используется во время маршалинга.  
  
 *riid*  
 Ссылка на идентификатор интерфейса для маршалинга. Этот интерфейс должен быть производным от `IUnknown` интерфейс.  
  
 *PV*  
 Указатель на указатель интерфейса, который должен быть маршалирован; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.  
  
 *dwDestContext*  
 Контекст назначения, где должен быть неупакованный указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Распаковка может произойти в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).  
  
 *pvDestContext*  
 Зарезервировано для будущего использования; должно иметь значение нуль.  
  
 *mshlflags*  
 Указывает, являются ли данные должны быть маршалированы для передачи обратно в клиентском процессе, типичный случай — диска или записываются на глобальной таблицы, где его можно получить несколькими клиентами.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Указатель на интерфейс был маршалирован успешно.  
  
 E_NOINTERFACE  
 Указанный интерфейс не поддерживается.  
  
 STG_E_MEDIUMFULL  
 Поток заполнен.  
  
 E_FAIL  
 Операция выполнена со сбоем.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)