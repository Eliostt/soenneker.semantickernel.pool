# Soenneker Semantic Kernel Pool 🎉

![GitHub Repo Size](https://img.shields.io/github/repo-size/Eliostt/soenneker.semantickernel.pool)
![GitHub Stars](https://img.shields.io/github/stars/Eliostt/soenneker.semantickernel.pool)
![GitHub Issues](https://img.shields.io/github/issues/Eliostt/soenneker.semantickernel.pool)
![GitHub License](https://img.shields.io/github/license/Eliostt/soenneker.semantickernel.pool)

Welcome to the **Soenneker Semantic Kernel Pool** repository! This project manages a pool of Semantic Kernel instances, complete with per-entry rate limiting. Whether you're building applications that require efficient resource management or simply exploring the capabilities of Semantic Kernel, this repository provides a solid foundation.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration Options](#configuration-options)
- [Rate Limiting](#rate-limiting)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Features

- **Pool Management**: Efficiently manages multiple instances of Semantic Kernel.
- **Rate Limiting**: Controls the rate of requests per entry to optimize performance.
- **Flexible Configuration**: Offers various options to tailor the pool to your needs.
- **Easy Integration**: Designed for seamless integration with .NET applications.

## Getting Started

To get started with the Soenneker Semantic Kernel Pool, you can clone this repository and follow the installation instructions. If you prefer, you can also check the [Releases](https://github.com/Eliostt/soenneker.semantickernel.pool/releases) section for downloadable files that you can execute.

## Installation

To install the Soenneker Semantic Kernel Pool, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/Eliostt/soenneker.semantickernel.pool.git
   cd soenneker.semantickernel.pool
   ```

2. Restore dependencies:
   ```bash
   dotnet restore
   ```

3. Build the project:
   ```bash
   dotnet build
   ```

4. If you prefer, you can download the latest release from the [Releases](https://github.com/Eliostt/soenneker.semantickernel.pool/releases) section. Just execute the downloaded file to get started.

## Usage

After installation, you can start using the Semantic Kernel Pool in your application. Here’s a simple example of how to initialize the pool and make requests:

```csharp
using Soenneker.SemanticKernel.Pool;

var kernelPool = new SemanticKernelPool();
kernelPool.Initialize();

// Make a request
var result = kernelPool.Request("Your input data");
Console.WriteLine(result);
```

### Configuration Options

You can customize the pool with various options. Here are some common configurations:

- **Max Instances**: Set the maximum number of kernel instances in the pool.
- **Rate Limit**: Define the rate limit for requests.
- **Timeout**: Specify a timeout for each request.

Example configuration:

```csharp
var options = new PoolOptions
{
    MaxInstances = 10,
    RateLimit = 5, // 5 requests per second
    Timeout = TimeSpan.FromSeconds(30)
};

var kernelPool = new SemanticKernelPool(options);
```

## Rate Limiting

Rate limiting is a crucial feature of the Soenneker Semantic Kernel Pool. It helps manage the load on your Semantic Kernel instances by controlling how many requests can be processed at a time. This prevents overloading the instances and ensures consistent performance.

### How It Works

When you make a request to the pool, it checks the current rate of requests against the defined limit. If the limit is reached, the request will be queued until it can be processed.

### Example

Here’s how you can implement rate limiting in your application:

```csharp
var kernelPool = new SemanticKernelPool(new PoolOptions { RateLimit = 5 });

for (int i = 0; i < 20; i++)
{
    var result = kernelPool.Request($"Input {i}");
    Console.WriteLine(result);
}
```

In this example, only 5 requests will be processed per second. The rest will wait until the rate limit allows them to proceed.

## Contributing

We welcome contributions to the Soenneker Semantic Kernel Pool! If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your changes to your forked repository.
5. Create a pull request.

We appreciate any help in improving this project.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Releases

For the latest updates and releases, please visit the [Releases](https://github.com/Eliostt/soenneker.semantickernel.pool/releases) section. You can download and execute the files to get started with the latest features and improvements.

---

Thank you for checking out the Soenneker Semantic Kernel Pool! We hope this project helps you manage your Semantic Kernel instances efficiently. If you have any questions or feedback, feel free to reach out. Happy coding!