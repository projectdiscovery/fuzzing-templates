

<h1 align="center">
Fuzzing Templates
</h1>
<h4 align="center">Community curated list of fuzzing templates for the nuclei engine to find unknown security vulnerabilities.</h4>


<p align="center">
<a href="https://github.com/projectdiscovery/fuzzing-templates/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat"></a>
<a href="https://twitter.com/pdnuclei"><img src="https://img.shields.io/twitter/follow/pdnuclei.svg?logo=twitter"></a>
<a href="https://discord.gg/projectdiscovery"><img src="https://img.shields.io/discord/695645237418131507.svg?logo=discord"></a>
</p>
      
<p align="center">
  <a href="https://nuclei.projectdiscovery.io/templating-guide/protocols/http-fuzzing/">Documentation</a> •
  <a href="https://github.com/projectdiscovery/fuzzing-templates/graphs/contributors">Contributions</a> •
  <a href="https://github.com/projectdiscovery/fuzzing-templates/discussions">Discussion</a> •
  <a href="https://discord.gg/projectdiscovery">Community</a>
</p>

----

Fuzzing templates are used with [nuclei](https://github.com/projectdiscovery/nuclei) scanner which powers the actual scanning engine. This repository contains various fuzzing templates for the scanner provided by our team, as well as contributed by the community.

We welcome contributions from the community through pull requests or issues to increase the coverage of security testing. Unlike the [nuclei-templates](https://github.com/projectdiscovery/nuclei-templates) project, which focuses on known vulnerabilities, fuzzing templates are specifically designed to **discover previously unknown vulnerabilities** in applications.


![image](https://user-images.githubusercontent.com/8293321/205839007-b18a1dc2-5b4e-4ee4-9051-c13b30089ee3.png)



📖 Documentation
-----

Please navigate to https://docs.nuclei.sh/template-guide/http/http-fuzzing for detailed documentation to **build your own fuzzing** template.
We have also added a set of templates to help you understand how things work.


🌪️ Using Fuzzing Templates
-----

1. **Install Nuclei**

```
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
```

2. **Clone Fuzzing Templates**

```
git clone https://github.com/projectdiscovery/fuzzing-templates.git
```

3. **Run Fuzzing Templates**

#### Input for fuzzing templates:

Current fuzzing support is limited to URLs with with query parameters, so any urls with no query parameters will be simply ignored.

```bash
$ cat fuzz_endpoints.txt

http://127.0.0.1:8082/info?name=test&another=value&random=data
http://127.0.0.1:8082/redirect?redirect_url=/info?name=redirected_from_url
http://127.0.0.1:8082/request?url=https://example.com
http://127.0.0.1:8082/email?text=important_user
http://127.0.0.1:8082/permissions?cmd=whoami
http://127.0.0.1:8082/info?name=redirected_from_url
```

> **Note**:

> *You can use [katana](https://github.com/projectdiscovery/katana) with query url filter (`-f qurl`) to get list of endpoints to run with url fuzzing templates* 

#### Running fuzzing templates:

```
nuclei -t fuzzing-templates -list fuzz_endpoints.txt
```

> **Note**:

> *You can use existing nuclei options to filter / run specific directory / sub directory / templates or tags* 

💬 Discussion
-----

Got questions / doubts / ideas to discuss?
Feel free to open a discussion on [GitHub discussions](https://github.com/projectdiscovery/fuzzing-templates/discussions) board.


👨‍💻 Community
-----

You are welcome to join the active [Discord Community](https://discord.gg/projectdiscovery) to discuss directly with project maintainers and share things with others around security and automation.
Additionally, you may follow us on [Twitter](https://twitter.com/pdnuclei) to be updated on all the things about Nuclei.


<p align="center">
<a href="https://github.com/projectdiscovery/fuzzing-templates/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=projectdiscovery/fuzzing-templates&max=300">
</a>
</p>


Thanks again for your contribution and keeping this community vibrant. ❤️
