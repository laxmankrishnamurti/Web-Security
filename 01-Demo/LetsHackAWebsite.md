# How to find security flaws(Vulnerabilities) in a website?

In Kali Linux there is a framework called "Metasploit". It is the most popular command line tool for testing the security of websites and checking for vulnerabilities. 

## There are currently 5677 Metasploit modules. These are :- 

1. auxiliary (1260)

- Auxiliary modules do not exploit a target, but can perform useful tasks such as:
    - Administration - Modify, operate, or manipulate something on target machine
    - Analyzing - Tools that perform analysis, mostly password cracking
    - Gathering - Gather, collect, or enumerate data from a single target
    - Denial of Service - Crash or slow a target machine or service
    - Scanning - Scan targets for known vulnerabilities
    - Server Support - Run Servers for common protocols such as SMB, FTP, etc


2. encoder (49) :: Encoders take the raw bytes of a payload and run some sort of encoding algorithm, like bitwise XOR. These modules are useful for encoding bad characters such as null bytes.

3. evasion (9) :: Evasion modules give Framework users the ability to generate evasive payloads that aim to evade AntiVirus, such as Windows Defender, without having to install external tools.

4. exploit (2405) :: Exploit modules are used to leverage vulnerabilities in a manner that allows the framework to execute arbitrary code. The arbitrary code that is executed is referred to as the payload.

5. nop (11) :: Nop modules, short for ‘No Operation’, generate a sequence of ‘No Operation’ instructions that perform no side-effects. NOPs are often used in conjunction with stack buffer overflows.

6. payload (1468) :: In the context of Metasploit exploit modules, payload modules encapsulate the arbitrary code (shellcode) that is executed as the result of an exploit succeeding. This normally involves the creation of a Metasploit session, but may instead execute code such as adding user accounts, or executing a simple pingback command that verifies that code execution was successful against a vulnerable target.

7. post (430) :: These modules are useful after a machine has been compromised and a Metasploit session has been opened. They perform useful tasks such as gathering, collecting, or enumerating data from a session.

[Read the Documentation](https://docs.metasploit.com/docs/modules.html)

## How to find vulnerabilities in a website. 

We have WMAP  plugin helps to find basic security flaws in a web-app.

## What is WMAP?

WMAP is a web vulnerability scanner that integrates with the Metasploit Framework. It is used for identifying and exploiting vulnerabilities in web applications. It was originally developed as a separate tool, but later integrated into Metasploit as a plugin to provide users with the ability to perform web application assessments within the Metasploit environment.

- WMAP is designed to scan web applications for common vulnerabilities like SQL injection, XSS (cross-site scripting), file inclusion, and more.

- LIMITATION :: It is not as advanced or feature-rich as standalone web scanners like OWASP ZAP or Burp Suite, but it allows you to find vulnerabilities and tie them directly to Metasploit's exploitation framework.

## How does WMAP works?

1. Website Discovery: WMAP first crawls the target website, mapping out its structure by identifying web pages, forms, links, and parameters.

2. Vulnerability Scanning: Once the site has been mapped, WMAP scans the web pages for common vulnerabilities. It can perform different kinds of tests, such as:
    - SQL Injection
    - Cross-Site Scripting (XSS)
    - File Inclusion
    - Directory Traversal
    - Unsecure Authentication Methods
    - And other common web vulnerabilities

3. Integration with Metasploit: Because WMAP is a plugin for Metasploit, you can directly take the information gathered by the WMAP scan and use it to run specific Metasploit modules to exploit the discovered vulnerabilities.

## How to use it?

1. Loading the Plugin :: Before using WMAP, we need to load it as a plugin inside Metasploit.

```bash
$ load wmap
```

2. Adding Websites and Targets :: To scan a website, we need to add the website as a target:

```bash
$ wmap_sites -a http://example.com
$ wmap_targets -t http://example.com
```

3. After adding targets, we can run the web vulnerability scan using:

```bash
$ wmap_run -e
```

4. After the scan completes, we can review the results using:

```bash
$ wmap_report -l
```

5. Exploitation: Since WMAP integrates with Metasploit, we can take any discovered vulnerabilities and directly exploit them using Metasploit modules. For example, if WMAP finds an SQL Injection vulnerability, we can search for an appropriate Metasploit module to exploit it:

```bash
$ search sql_injection
```