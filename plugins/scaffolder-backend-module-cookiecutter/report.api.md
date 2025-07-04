## API Report File for "@backstage/plugin-scaffolder-backend-module-cookiecutter"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { BackendFeature } from '@backstage/backend-plugin-api';
import { objectOutputType } from 'zod';
import { ScmIntegrations } from '@backstage/integration';
import { TemplateAction } from '@backstage/plugin-scaffolder-node';
import { UrlReaderService } from '@backstage/backend-plugin-api';
import { Writable } from 'stream';
import { ZodTypeAny } from 'zod';

// @public
export interface ContainerRunner {
  runContainer(opts: {
    imageName: string;
    command?: string | string[];
    args: string[];
    logStream?: Writable;
    mountDirs?: Record<string, string>;
    workingDir?: string;
    envVars?: Record<string, string>;
    pullImage?: boolean;
    defaultUser?: boolean;
    pullOptions?: {
      authconfig?: {
        username?: string;
        password?: string;
        auth?: string;
        email?: string;
        serveraddress?: string;
        [key: string]: unknown;
      };
      [key: string]: unknown;
    };
  }): Promise<void>;
}

// @public
const cookiecutterModule: BackendFeature;
export default cookiecutterModule;

// @public
export function createFetchCookiecutterAction(options: {
  reader: UrlReaderService;
  integrations: ScmIntegrations;
  containerRunner?: ContainerRunner;
}): TemplateAction<
  {
    url: string;
    values: objectOutputType<{}, ZodTypeAny, 'passthrough'>;
    targetPath?: string | undefined;
    copyWithoutRender?: string[] | undefined;
    extensions?: string[] | undefined;
    imageName?: string | undefined;
  },
  {
    [x: string]: any;
  },
  'v2'
>;
```
