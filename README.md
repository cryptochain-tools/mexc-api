#### Installation: **`npm install mexc-api`**
[![npm install mexc-api](https://nodei.co/npm/mexc-api.png?mini=true)](https://npmjs.org/package/mexc-api)

#### Getting started
```typescript
import { Spot, Contract } from 'mexc-api'


const spot = new Spot({
    apiKey: process.env.API_KEY,
    apiSecret: process.env.SECRET_KEY
});

const contract = new Contract({
    apiKey: process.env.API_KEY,
    apiSecret: process.env.SECRET_KEY
});
```

#### Spot
```typescript
    await spot.symbols();
    await spot.serverTime();
    await spot.ping();
    await spot.defaultSymbols();
    await spot.ticker({
        symbol?: string;
    });
    await spot.depthV2({
        symbol?: string;
        depth?: number;
    });
    await spot.deals({
        symbol: string;
        limit?: number;
    });
    await spot.klineV2({
        symbol: string;
        interval: string;
        start_time?: string;
        limit: string;
    });
    await spot.coinList({
        currency?: string;
    });
    await spot.account();
    await spot.apiAccount();
    await spot.placeOrder({
        client_order_id?: string;
        order_type: string;
        price: string;
        quantity: string;
        symbol: string;
        trade_type: string;
    });
    await spot.cancelOrderV2({
        order_ids: string;
        client_order_ids: string;
    });
    await spot.multiPlaceOrder({
        order_type: string;
        price: string;
        quantity: string;
        symbol: string;
        trade_type: string;
    }[]);
    await spot.getOpenOrder({
        symbol: string;
    });
    await spot.getAllOrder({
        states: string;
        symbol: string;
        trade_type: string;
    });
    await spot.queryOrderById({
        order_ids: string;
    });
    await spot.getOrderDeal({
        limit: string;
        start_time: string;
        symbol: string;
    });
    await spot.queryOrderDealById({
        order_id: string;
    });
    await spot.cancelBySymbol({
        symbol: string;
    });
    await spot.getDepositList({
        currency: string;
    });
    await spot.getDepositRecord({
        currency: string;
        start_time: string;
        end_time: string;
    });
    await spot.getWithdrawList({
        start_time: string;
        end_time: string;
        withdraw_id: string;
    });
    await spot.withdraw({
        currency: string;
        chain: string;
        amount: string;
        address: string;
    });
    await spot.transFer({
        sub_uid: string;
        currency: string;
        amount: string;
        type: string;
    });
    await spot.getTransferRecord({
        start_time: string;
        end_time: string;
    });
    await spot.getAvlTransfer({
        currency: string;
    });
    await spot.queryTransferRecordById({
        transact_id: string;
    });
    await spot.pingV3();
    await spot.serverTimeV3();
    await spot.exchangeInformation();
    await spot.depth({
        symbol: string;
    });
    await spot.recentTradesList({
        symbol: string;
    });
    await spot.oldTradeLookup({
        symbol: string;
    });
    await spot.compressedTradesList({
        symbol: string;
    });
    await spot.kline({
        symbol: string;
        interval: string;
    });
    await spot.currentAveragePrice({
        symbol: string;
    });
    await spot.tickerPriceChange();
    await spot.symbolPriceTicker();
    await spot.symbolOrderBook();
    await spot.etfInfo();
    await spot.testConnectivity({
        symbol: string;
        side: string;
        type: string;
        quantity: string;
        price: string;
    });
    await spot.order({
        symbol: string;
        side: string;
        type: string;
        quantity: string;
        price: string;
        quoteOrderQty: string;
    });
    await spot.cancelOrder({
        symbol: string;
        orderId: string;
    });
    await spot.cancelAllOpenOrders({
        symbol: string;
    });
    await spot.queryOrder({
        symbol: string;
        orderId: string;
    });
    await spot.currentOpenOrders({
        symbol: string;
    });
    await spot.allOrders({
        symbol: string;
    });
    await spot.accountInformation();
    await spot.accountTradeList({
        symbol: string;
    });
```

#### Contract
```typescript
    await contract.serverTime();
    await contract.contractDetail();
    await contract.supportCurrencies();
    await contract.depthBySymbol({
        symbol: string;
    });
    await contract.depthCommitsBySymbol({
        symbol: string;
        limit: string;
    });
    await contract.indexPriceBySymbol({
        symbol: string;
    });
    await contract.fairPriceBySymbol({
        symbol: string;
    });
    await contract.fundingRateBySymbol({
        symbol: string;
    });
    await contract.klineBySymbol({
        symbol: string;
    });
    await contract.indexPriceKlineBySymbol({
        symbol: string;
    });
    await contract.fairPriceKlineBySymbol({
        symbol: string;
    });
    await contract.dealsBySymbol({
        symbol: string;
    });
    await contract.ticker({
        symbol?: string;
    });
    await contract.riskReverse({
        symbol?: string;
    });
    await contract.riskReverseHistory({
        symbol: string;
        page_num: string;
        page_size: string;
    });
    await contract.fundingRateHistory({
        symbol: string;
        page_num: string;
        page_size: string;
    });
    await contract.assets();
    await contract.assetByCurrency({
        currency: string;
    });
    await contract.transferRecord({
        page_num: string;
        page_start: string;
    });
    await contract.historyPositions({
        page_num: string;
        page_start: string;
    });
    await contract.openPositions({
        symbol: string;
    });
    await contract.fundingRecords({
        symbol?: string;
        position_id?: string;
        page_num: string;
        page_size: string;
    });
    await contract.openOrders({
        symbol: string;
        page_num: string;
        page_size: string;
    });
    await contract.historyOrders({
        symbol: string;
        states: string;
        category: number;
        start_time: string;
        end_time: string;
        side: string;
        page_num: string;
        page_size: string;
    });
    await contract.externalByExternalOid({
        symbol: string;
        external_oid: string;
    });
    await contract.queryOrderById({
        order_id: string;
    });
    await contract.batchQueryById({
        order_ids: string;
    });
    await contract.dealDetails({
        order_id: string;
    });
    await contract.orderDeals({
        symbol: string;
        start_time: string;
        end_time: string;
        page_num: string;
        page_size: string;
    });
    await contract.planOrder({
        symbol: string;
        states: string;
        start_time: string;
        end_time: string;
        page_num: string;
        page_size: string;
    });
    await contract.stopOrder({
        symbol: string;
        is_finished: string;
        start_time: string;
        end_time: string;
        page_num: string;
        page_size: string;
    });
    await contract.riskLimit({
        symbol: string;
    });
    await contract.tieredFeeRate({
        symbol: string;
    });
    await contract.changeMargin({
        positionId: string;
        amount: string;
        type: string;
    });
    await contract.leverage({
        symbol: string;
    });
    await contract.changeLeverage({
        positionId: string;
        leverage: string;
        openType: string;
        symbol: string;
        positionType: string;
    });
    await contract.getPositionMode();
    await contract.changePositionMode({
        positionMode: 1 | 2;
    });
    await contract.placeNewOrder({
        symbol: string;
        price: string;
        vol: string;
        leverage: string;
        side: string;
        type: string;
        openType: string;
        positionId: string;
        externalOid: string;
        stopLossPrice: string;
        takeProfitPrice: string;
        positionMode: string;
        reduceOnly: string;
    });
    await contract.placeNewOrderBatch({
        symbol: string;
        price: string;
        vol: string;
        leverage: string;
        side: string;
        type: string;
        openType: string;
        positionId: string;
        externalOid: string;
        stopLossPrice: string;
        takeProfitPrice: string;
        positionMode: string;
        reduceOnly: string;
    }[]);
    await contract.cancelOrderById(string[]);
    await contract.cancelWithExternal({
        symbol: string;
        externalOid: string;
    });
    await contract.cancelAll({
        symbol: string;
    });
    await contract.cancelPlanOrder(string[]);
    await contract.cancelAllPlanOrder({
        symbol: string;
    });
    await contract.cancelStopOrder({
        stopPlanOrderId: string;
    });
    await contract.cancelAllStopOrder({
        symbol: string;
        positionId: string;
    });
    await contract.stopOrderChangePrice({
        orderId: string;
        stopLossPrice: string;
        takeProfitPrice: string;
    });
    await contract.stopOrderChangePlanPrice({
        stopPlanOrderId: string;
        stopLossPrice: string;
        takeProfitPrice: string;
    });
```
