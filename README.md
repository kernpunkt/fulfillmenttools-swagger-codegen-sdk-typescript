# fulfillmenttools-swagger-codegen-sdk-typescript
This SDK was created with swagger-codegen from https://raw.githubusercontent.com/fulfillmenttools/fulfillmenttools-api-reference/master/api.swagger.yaml with openapi version 3.0.1

## examples

```ts
import {
    CoreConfigurationApi,
    CoreCustomServicesApi,
    CoreDocumentSetsApi,
    CoreEventingApi,
    CoreExpiriesApi,
    CoreFacilitiesApi,
    CoreListingsApi,
    CoreNotificationCenterApi,
    CoreProcessesApi,
    CoreProcessesExternalActionsApi,
    CoreProcessesExternalActionsLogsApi,
    CoreRemoteConfigurationApi,
    CoreTagsApi,
    CoreUserManagementApi,
    CoreValidationsApi,
    DOMSCancelationReasonsApi,
    DOMSCheckoutOptionsApi,
    DOMSOrdersApi,
    DOMSRoutingPlansApi,
    FulfillmentOperationsCustomServicesApi,
    FulfillmentOperationsHandoverApi,
    FulfillmentOperationsOperativeProcessApi,
    FulfillmentOperationsPackingApi,
    FulfillmentOperationsRestowApi,
    FulfillmentOperationsReturnsApi,
    FulfillmentOperationsShipmentsApi,
    InfrastructureArtifactsApi,
    InfrastructureFeaturesApi,
    InfrastructureGraphQLApi,
    InfrastructureHealthApi,
    InfrastructureOIDCConfigurationApi,
    InventoryManagementChannelAvailabilityApi,
    InventoryManagementInboundApi,
    InventoryManagementStocksApi,
    LastMileIntegrationCarriersApi
} from "fulfillmenttools-swagger-codegen-sdk-typescript";

const fftAuthUrl = "https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=";
const fftApiUser: string = process.env.FFT_API_USER;
const fftApiKey: string = process.env.FFT_API_KEY;
const fftApiPwd: string = process.env.FFT_API_PWD;
const fftApiUrl: string = process.env.FFT_API_URL;

const getFetcher = (bearerToken: string) => {
    return (url: string): Promise<Response> => fetch(url, {
        cache: "no-store",
        headers: {
            Authorization: `Bearer ${ bearerToken }`,
            "Cache-Control": "no-cache",
        }
    });
};

const getFftAuthInfo = async () => {
    const authResponse = await fetch(fftAuthUrl + encodeURIComponent(fftApiKey), {
        method: "POST",
        body: JSON.stringify({
            email: fftApiUser + "@" + fftProjectId + ".com",
            password: fftApiPwd,
            returnSecureToken: true,
        }),
        headers: {
            "Content-Type": "application/json",
            "Cache-Control": "no-cache",
        }
    });

    return await authResponse.json();
};

const authInfo = await getFftAuthInfo();
const f = getFetcher(authInfo.idToken);

// Examples to instantiate different APIs
new CoreConfigurationApi({}, fftApiUrl, f);
new CoreCustomServicesApi({}, fftApiUrl, f);
new CoreDocumentSetsApi({}, fftApiUrl, f);
new CoreEventingApi({}, fftApiUrl, f);
new CoreExpiriesApi({}, fftApiUrl, f);
new CoreFacilitiesApi({}, fftApiUrl, f);
new CoreListingsApi({}, fftApiUrl, f);
new CoreNotificationCenterApi({}, fftApiUrl, f);
new CoreProcessesApi({}, fftApiUrl, f);
new CoreProcessesExternalActionsApi({}, fftApiUrl, f);
new CoreProcessesExternalActionsLogsApi({}, fftApiUrl, f);
new CoreRemoteConfigurationApi({}, fftApiUrl, f);
new CoreTagsApi({}, fftApiUrl, f);
new CoreUserManagementApi({}, fftApiUrl, f);
new CoreValidationsApi({}, fftApiUrl, f);
new DOMSCancelationReasonsApi({}, fftApiUrl, f);
new DOMSCheckoutOptionsApi({}, fftApiUrl, f);
new DOMSOrdersApi({}, fftApiUrl, f);
new DOMSRoutingPlansApi({}, fftApiUrl, f);
new FulfillmentOperationsCustomServicesApi({}, fftApiUrl, f);
new FulfillmentOperationsHandoverApi({}, fftApiUrl, f);
new FulfillmentOperationsOperativeProcessApi({}, fftApiUrl, f);
new FulfillmentOperationsPackingApi({}, fftApiUrl, f);
new FulfillmentOperationsPickingApi({}, fftApiUrl, f);
new FulfillmentOperationsRestowApi({}, fftApiUrl, f);
new FulfillmentOperationsReturnsApi({}, fftApiUrl, f);
new FulfillmentOperationsShipmentsApi({}, fftApiUrl, f);
new InfrastructureArtifactsApi({}, fftApiUrl, f);
new InfrastructureFeaturesApi({}, fftApiUrl, f);
new InfrastructureGraphQLApi({}, fftApiUrl, f);
new InfrastructureHealthApi({}, fftApiUrl, f);
new InfrastructureOIDCConfigurationApi({}, fftApiUrl, f);
new InventoryManagementChannelAvailabilityApi({}, fftApiUrl, f);
new InventoryManagementInboundApi({}, fftApiUrl, f);
new InventoryManagementStocksApi({}, fftApiUrl, f);
new LastMileIntegrationCarriersApi({}, fftApiUrl, f);
```