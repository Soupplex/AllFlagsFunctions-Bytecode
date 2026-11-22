FFlag     : DFFlagDebugDisableVoxelAsyncReadMeshing
RVA .data : 0x811b3e8
XREFs     : 1 total (1 em runtime)
Insn RVA  : 0x380e032
Operação  : 0x380e032: cmp byte [flag], imm8 ; fn=0x380e000..0x380e415

[Disassembly .text]
  === [Resumo do Efeito da FFlag no Engine (RBX::DebugDisable)] ===
    Classe  : RBX::DebugDisable (RTTI Resolvido)
    Padrão  : DFFlagDebugDisableVoxelAsyncReadMeshing = false (default) [bool, mode=2]
    Papel   : Chave condicional (if/else gate) que ativa ou desativa este bloco de execução
    [Child @0x374f270] Papel   : Chave condicional (if/else gate) que ativa ou desativa este bloco de execução
  
  === [Decompilacao C++ da Funcao 0x380e000..0x380e415] ===
    // Flag defaults: DebugDisableVoxelAsyncReadMeshing = false
    void RBX::DebugDisable::func_0x380e000(RBX::DebugDisable* this, int64_t param_2) {
      (rax & 0x48)->field_0x0 = param_2;
      call_0x371d9e0(r15);
      if (rsi->field_0x8 != 0) {
        call_0x6daf40(rsi->field_0x8);
      }
      if (r12->field_0x8 != 0) {
        call_0x6daf40(r12->field_0x8);
      }
      if (rdi->field_0x8 != 0 && atomic_fetch_add(&rdi->field_0x8->field_0xc, r14) == 1) {
        rdi->field_0x8->vfunc_0x8() // -> boost::program_options::invalid_option_value::fn_0x35074e0;
      }
      if (r13->field_0x8 != 0) {
        call_0x6daf40(r13->field_0x8);
      }
      if (frame_m0x38->field_0x8 != 0) {
        call_0x6daf40(frame_m0x38->field_0x8);
      }
    }
  
  === [Instrucoes x86-64 Decodificadas (Alinhadas por RVA & Bytes)] ===
    0x380e000 | 54                       | push rsp
    0x380e001 | 24 48                    | and al, 0x48
    0x380e003 | 48 89 10                 | mov qword ptr [rax], rdx
    0x380e006 | 48 8b 44 24 48           | mov rax, qword ptr [rsp + 0x48]
    0x380e00b | 48 85 c0                 | test rax, rax
    0x380e00e | 74 07                    | je 0x380e017
    0x380e010 | 48 c7 00 00 00 00 00     | mov qword ptr [rax], 0x0
    L_0x380e017:
    0x380e017 | 48 c7 44 24 50 00 00 00.. | mov qword ptr [rsp + 0x50], 0x0
    0x380e020 | e9 61 03 00 00           | jmp 0x380e386
    0x380e025 | 49 8b 87 c0 00 00 00     | mov rax, qword ptr [r15 + 0xc0]
    0x380e02c | 80 78 15 00              | cmp byte ptr [rax + 0x15], 0x0
    0x380e030 | 74 1f                    | je 0x380e051
    0x380e032 | 80 3d af d3 90 04 00     | cmp byte ptr [rip + 0x490d3af], 0x0 ; DFFlagDebugDisableVoxelAsyncReadMeshing
    0x380e039 | 75 16                    | jne 0x380e051
    0x380e03b | 4c 8b cb                 | mov r9, rbx
    0x380e03e | 4d 8b c5                 | mov r8, r13
    0x380e041 | 49 8b d4                 | mov rdx, r12
    0x380e044 | 49 8b cf                 | mov rcx, r15
    0x380e047 | e8 54 76 ff ff           | call 0x38056a0
    0x380e04c | e9 dc 00 00 00           | jmp 0x380e12d
    L_0x380e051:
    0x380e051 | 49 8b d7                 | mov rdx, r15
    0x380e054 | 48 8d 4d 40              | lea rcx, [rbp + 0x40]
    0x380e058 | e8 03 6c ff ff           | call 0x3804c60
    0x380e05d | 90                       | nop
    0x380e05e | 80 bd 88 02 00 00 00     | cmp byte ptr [rbp + 0x288], 0x0
    0x380e065 | 0f 84 86 00 00 00        | je 0x380e0f1
    0x380e06b | 49 8b d7                 | mov rdx, r15
    0x380e06e | 48 8d 8d a0 02 00 00     | lea rcx, [rbp + 0x2a0]
    0x380e075 | e8 66 0f f4 ff           | call 0x374efe0
    0x380e07a | 90                       | nop
    0x380e07b | 48 8d 55 40              | lea rdx, [rbp + 0x40]
    0x380e07f | 48 8d 8d a0 03 00 00     | lea rcx, [rbp + 0x3a0]
    0x380e086 | e8 e5 11 f4 ff           | call 0x374f270
    0x380e08b | 90                       | nop
    0x380e08c | 48 8d 95 a0 02 00 00     | lea rdx, [rbp + 0x2a0]
    0x380e093 | 49 8b 4d 00              | mov rcx, qword ptr [r13]
    0x380e097 | e8 94 45 00 00           | call 0x3812630
    0x380e09c | 90                       | nop
    0x380e09d | 4c 8d 0d 6c 90 f3 ff     | lea r9, [rip - 0xc6f94]
    0x380e0a4 | ba 80 00 00 00           | mov edx, 0x80
    0x380e0a9 | 44 8d 42 83              | lea r8d, [rdx - 0x7d]
    0x380e0ad | 48 8d 8d 60 04 00 00     | lea rcx, [rbp + 0x460]
    0x380e0b4 | e8 b7 68 5d 02           | call 0x5de4970
    0x380e0b9 | 48 8b 8d 20 04 00 00     | mov rcx, qword ptr [rbp + 0x420]
    0x380e0c0 | 48 85 c9                 | test rcx, rcx
    0x380e0c3 | 74 05                    | je 0x380e0ca
    0x380e0c5 | e8 76 ce ec fc           | call 0x6daf40
    L_0x380e0ca:
    0x380e0ca | 48 8d 85 e0 03 00 00     | lea rax, [rbp + 0x3e0]
    0x380e0d1 | 48 8b 8d d0 03 00 00     | mov rcx, qword ptr [rbp + 0x3d0]
    0x380e0d8 | 48 3b c8                 | cmp rcx, rax
    0x380e0db | 74 06                    | je 0x380e0e3
    0x380e0dd | e8 de 79 14 01           | call 0x4955ac0
    0x380e0e2 | 90                       | nop
    L_0x380e0e3:
    0x380e0e3 | 48 8d 8d a0 02 00 00     | lea rcx, [rbp + 0x2a0]
    0x380e0ea | e8 f1 f8 f0 ff           | call 0x371d9e0
    0x380e0ef | eb 27                    | jmp 0x380e118
    L_0x380e0f1:
    0x380e0f1 | f2 41 0f 10 07           | movsd xmm0, qword ptr [r15]
    0x380e0f6 | f2 0f 11 45 00           | movsd qword ptr [rbp], xmm0
    0x380e0fb | 41 8b 47 08              | mov eax, dword ptr [r15 + 0x8]
    0x380e0ff | 89 45 08                 | mov dword ptr [rbp + 0x8], eax
    0x380e102 | 41 0f b6 47 0c           | movzx eax, byte ptr [r15 + 0xc]
    0x380e107 | 89 45 0c                 | mov dword ptr [rbp + 0xc], eax
    0x380e10a | 48 8d 55 00              | lea rdx, [rbp]
    0x380e10e | 49 8b 0c 24              | mov rcx, qword ptr [r12]
    0x380e112 | e8 c9 45 00 00           | call 0x38126e0
    0x380e117 | 90                       | nop
    L_0x380e118:
    0x380e118 | 80 bd 88 02 00 00 00     | cmp byte ptr [rbp + 0x288], 0x0
    0x380e11f | 74 09                    | je 0x380e12a
    0x380e121 | 48 8d 4d 40              | lea rcx, [rbp + 0x40]
    0x380e125 | e8 f6 57 00 00           | call 0x3813920
    L_0x380e12a:
    0x380e12a | f0 ff 0b                 | lock dec dword ptr [rbx]
    L_0x380e12d:
    0x380e12d | 48 83 7c 24 68 ff        | cmp qword ptr [rsp + 0x68], -0x1
    0x380e133 | 0f 84 26 02 00 00        | je 0x380e35f
    0x380e139 | 48 8b 45 a8              | mov rax, qword ptr [rbp - 0x58]
    0x380e13d | 33 f6                    | xor esi, esi
    0x380e13f | 48 85 c0                 | test rax, rax
    0x380e142 | 74 45                    | je 0x380e189
    0x380e144 | 8b d6                    | mov edx, esi
    0x380e146 | 48 83 7d b0 01           | cmp qword ptr [rbp - 0x50], 0x1
    0x380e14b | 0f 94 c2                 | sete dl
    0x380e14e | 48 83 c2 02              | add rdx, 0x2
    0x380e152 | 48 c1 e2 30              | shl rdx, 0x30
    0x380e156 | 48 b9 ff ff ff ff ff ff.. | mov rcx, 0xffffffffffff
    0x380e160 | 48 23 c1                 | and rax, rcx
    0x380e163 | 48 0b d0                 | or rdx, rax
    0x380e166 | 48 89 75 e8              | mov qword ptr [rbp - 0x18], rsi
    0x380e16a | 48 8d 45 e8              | lea rax, [rbp - 0x18]
    0x380e16e | 48 89 44 24 28           | mov qword ptr [rsp + 0x28], rax
    0x380e173 | 48 89 74 24 20           | mov qword ptr [rsp + 0x20], rsi
    0x380e178 | 45 33 c9                 | xor r9d, r9d
    0x380e17b | 45 33 c0                 | xor r8d, r8d
    0x380e17e | b1 21                    | mov cl, 0x21
    0x380e180 | e8 5b 61 19 ff           | call 0x29a42e0
    0x380e185 | 48 89 75 b0              | mov qword ptr [rbp - 0x50], rsi
    L_0x380e189:
    0x380e189 | 80 3d 46 63 c9 04 00     | cmp byte ptr [rip + 0x4c96346], 0x0
    0x380e190 | 0f 84 eb 00 00 00        | je 0x380e281
    0x380e196 | 80 3d 83 5d 8f 04 00     | cmp byte ptr [rip + 0x48f5d83], 0x0 ; DFFlagMicroProfilerMemoryScope
    0x380e19d | 0f 84 de 00 00 00        | je 0x380e281
    0x380e1a3 | e8 f8 1c 17 01           | call 0x497fea0
    0x380e1a8 | 48 8b 08                 | mov rcx, qword ptr [rax]
    0x380e1ab | 48 85 c9                 | test rcx, rcx
    0x380e1ae | 75 04                    | jne 0x380e1b4
    0x380e1b0 | 48 8d 48 08              | lea rcx, [rax + 0x8]
    L_0x380e1b4:
    0x380e1b4 | 8b 11                    | mov edx, dword ptr [rcx]
    0x380e1b6 | 44 8b 41 04              | mov r8d, dword ptr [rcx + 0x4]
    0x380e1ba | 4c 8b 49 08              | mov r9, qword ptr [rcx + 0x8]
    0x380e1be | 4c 8b 59 10              | mov r11, qword ptr [rcx + 0x10]
    0x380e1c2 | 8b 4d 98                 | mov ecx, dword ptr [rbp - 0x68]
    0x380e1c5 | 85 c9                    | test ecx, ecx
    0x380e1c7 | 74 45                    | je 0x380e20e
    0x380e1c9 | 48 8b 7d 88              | mov rdi, qword ptr [rbp - 0x78]
    0x380e1cd | 4c 3b cf                 | cmp r9, rdi
    0x380e1d0 | 72 3c                    | jb 0x380e20e
    0x380e1d2 | 48 8b 5d 90              | mov rbx, qword ptr [rbp - 0x70]
    0x380e1d6 | 4c 3b db                 | cmp r11, rbx
    0x380e1d9 | 72 33                    | jb 0x380e20e
    0x380e1db | 3b d1                    | cmp edx, ecx
    0x380e1dd | 72 2f                    | jb 0x380e20e
    0x380e1df | 44 8b 55 9c              | mov r10d, dword ptr [rbp - 0x64]
    0x380e1e3 | 45 3b c2                 | cmp r8d, r10d
    0x380e1e6 | 72 26                    | jb 0x380e20e
    0x380e1e8 | 49 8b c1                 | mov rax, r9
    0x380e1eb | 48 2b c7                 | sub rax, rdi
    0x380e1ee | 48 01 44 24 70           | add qword ptr [rsp + 0x70], rax
    0x380e1f3 | 49 8b c3                 | mov rax, r11
    0x380e1f6 | 48 2b c3                 | sub rax, rbx
    0x380e1f9 | 48 01 44 24 78           | add qword ptr [rsp + 0x78], rax
    0x380e1fe | 8b c2                    | mov eax, edx
    0x380e200 | 2b c1                    | sub eax, ecx
    0x380e202 | 01 45 80                 | add dword ptr [rbp - 0x80], eax
    0x380e205 | 41 8b c0                 | mov eax, r8d
    0x380e208 | 41 2b c2                 | sub eax, r10d
    0x380e20b | 01 45 84                 | add dword ptr [rbp - 0x7c], eax
    L_0x380e20e:
    0x380e20e | 48 8b 44 24 48           | mov rax, qword ptr [rsp + 0x48]
    0x380e213 | 48 85 c0                 | test rax, rax
    0x380e216 | 74 0f                    | je 0x380e227
    0x380e218 | 4c 89 48 48              | mov qword ptr [rax + 0x48], r9
    0x380e21c | 4c 89 58 50              | mov qword ptr [rax + 0x50], r11
    0x380e220 | 89 50 58                 | mov dword ptr [rax + 0x58], edx
    0x380e223 | 44 89 40 5c              | mov dword ptr [rax + 0x5c], r8d
    L_0x380e227:
    0x380e227 | 48 8b 55 80              | mov rdx, qword ptr [rbp - 0x80]
    0x380e22b | 81 e2 ff ff ff 00        | and edx, 0xffffff
    0x380e231 | 48 c1 e2 18              | shl rdx, 0x18
    0x380e235 | 8b 45 84                 | mov eax, dword ptr [rbp - 0x7c]
    0x380e238 | 25 ff ff ff 00           | and eax, 0xffffff
    0x380e23d | 48 0b d0                 | or rdx, rax
    0x380e240 | 48 8b 4c 24 70           | mov rcx, qword ptr [rsp + 0x70]
    0x380e245 | 48 c1 e1 20              | shl rcx, 0x20
    0x380e249 | 8b 44 24 78              | mov eax, dword ptr [rsp + 0x78]
    0x380e24d | 48 0b c8                 | or rcx, rax
    0x380e250 | 48 89 4d f8              | mov qword ptr [rbp - 0x8], rcx
    0x380e254 | 48 85 d2                 | test rdx, rdx
    0x380e257 | 75 05                    | jne 0x380e25e
    0x380e259 | 48 85 c9                 | test rcx, rcx
    0x380e25c | 74 23                    | je 0x380e281
    L_0x380e25e:
    0x380e25e | 48 89 75 f0              | mov qword ptr [rbp - 0x10], rsi
    0x380e262 | 48 8d 45 f0              | lea rax, [rbp - 0x10]
    0x380e266 | 48 89 44 24 28           | mov qword ptr [rsp + 0x28], rax
    0x380e26b | 48 89 74 24 20           | mov qword ptr [rsp + 0x20], rsi
    0x380e270 | 41 b9 08 00 00 00        | mov r9d, 0x8
    0x380e276 | 4c 8d 45 f8              | lea r8, [rbp - 0x8]
    0x380e27a | b1 14                    | mov cl, 0x14
    0x380e27c | e8 5f 60 19 ff           | call 0x29a42e0
    L_0x380e281:
    0x380e281 | 48 8b 74 24 50           | mov rsi, qword ptr [rsp + 0x50]
    0x380e286 | 48 83 7c 24 68 ff        | cmp qword ptr [rsp + 0x68], -0x1
    0x380e28c | 0f 84 98 00 00 00        | je 0x380e32a
    0x380e292 | e8 29 39 19 ff           | call 0x29a1bc0
    0x380e297 | 48 8b 18                 | mov rbx, qword ptr [rax]
    0x380e29a | 48 85 db                 | test rbx, rbx
    0x380e29d | 0f 84 87 00 00 00        | je 0x380e32a
    0x380e2a3 | 48 8b ce                 | mov rcx, rsi
    0x380e2a6 | 48 c1 e9 0e              | shr rcx, 0xe
    0x380e2aa | 0f 31                    | rdtsc
    0x380e2ac | 48 c1 e2 20              | shl rdx, 0x20
    0x380e2b0 | 48 0b c2                 | or rax, rdx
    0x380e2b3 | 48 8b f8                 | mov rdi, rax
    0x380e2b6 | 48 2b 3d 73 c3 4c 05     | sub rdi, qword ptr [rip + 0x54cc373]
    0x380e2bd | 48 8b 05 84 f3 95 04     | mov rax, qword ptr [rip + 0x495f384]
    0x380e2c4 | 48 85 88 b8 00 00 00     | test qword ptr [rax + 0xb8], rcx
    0x380e2cb | 74 4c                    | je 0x380e319
    0x380e2cd | 80 bb 65 05 00 00 00     | cmp byte ptr [rbx + 0x565], 0x0
    0x380e2d4 | 74 54                    | je 0x380e32a
    0x380e2d6 | 48 8b 80 a0 d5 26 00     | mov rax, qword ptr [rax + 0x26d5a0]
    0x380e2dd | 48 85 c0                 | test rax, rax
    0x380e2e0 | 75 07                    | jne 0x380e2e9
    0x380e2e2 | b8 ff ff ff ff           | mov eax, 0xffffffff
    0x380e2e7 | eb 0a                    | jmp 0x380e2f3
    L_0x380e2e9:
    0x380e2e9 | 48 8b 4b 30              | mov rcx, qword ptr [rbx + 0x30]
    0x380e2ed | ff 15 4d ba c2 02        | call qword ptr [rip + 0x2c2ba4d] ; __guard_dispatch_icall_fptr (0x6439d40)
    L_0x380e2f3:
    0x380e2f3 | 8b d0                    | mov edx, eax
    0x380e2f5 | 4c 8b 0d 1c b8 c6 04     | mov r9, qword ptr [rip + 0x4c6b81c]
    0x380e2fc | 45 33 c0                 | xor r8d, r8d
    0x380e2ff | 48 8b ce                 | mov rcx, rsi
    0x380e302 | e8 f9 55 19 ff           | call 0x29a3900
    0x380e307 | 8b 4b 44                 | mov ecx, dword ptr [rbx + 0x44]
    0x380e30a | 4c 8b 0d 07 b8 c6 04     | mov r9, qword ptr [rip + 0x4c6b807]
    0x380e311 | 41 b8 04 00 00 00        | mov r8d, 0x4
    0x380e317 | eb 09                    | jmp 0x380e322
    L_0x380e319:
    0x380e319 | 4c 8b cb                 | mov r9, rbx
    0x380e31c | 45 33 c0                 | xor r8d, r8d
    0x380e31f | 48 8b ce                 | mov rcx, rsi
    L_0x380e322:
    0x380e322 | 48 8b d7                 | mov rdx, rdi
    0x380e325 | e8 d6 55 19 ff           | call 0x29a3900
    L_0x380e32a:
    0x380e32a | 48 8b 44 24 50           | mov rax, qword ptr [rsp + 0x50]
    0x380e32f | 48 c1 e8 0e              | shr rax, 0xe
    0x380e333 | 48 23 05 be b2 e1 04     | and rax, qword ptr [rip + 0x4e1b2be]
    0x380e33a | 48 85 05 37 b3 e1 04     | test qword ptr [rip + 0x4e1b337], rax
    0x380e341 | 74 12                    | je 0x380e355
    0x380e343 | 48 8b 05 1e ec cc 04     | mov rax, qword ptr [rip + 0x4ccec1e]
    0x380e34a | 48 85 c0                 | test rax, rax
    0x380e34d | 74 06                    | je 0x380e355
    0x380e34f | ff 15 eb b9 c2 02        | call qword ptr [rip + 0x2c2b9eb] ; __guard_dispatch_icall_fptr (0x6439d40)
    L_0x380e355:
    0x380e355 | 48 8b 7c 24 30           | mov rdi, qword ptr [rsp + 0x30]
    0x380e35a | 48 8b 74 24 38           | mov rsi, qword ptr [rsp + 0x38]
    L_0x380e35f:
    0x380e35f | e8 6c 60 11 ff           | call 0x29243d0
    0x380e364 | 48 8b 4c 24 48           | mov rcx, qword ptr [rsp + 0x48]
    0x380e369 | 48 89 08                 | mov qword ptr [rax], rcx
    0x380e36c | 48 8b 44 24 48           | mov rax, qword ptr [rsp + 0x48]
    0x380e371 | 48 85 c0                 | test rax, rax
    0x380e374 | 74 07                    | je 0x380e37d
    0x380e376 | 48 c7 00 00 00 00 00     | mov qword ptr [rax], 0x0
    L_0x380e37d:
    0x380e37d | 48 c7 44 24 50 00 00 00.. | mov qword ptr [rsp + 0x50], 0x0
    L_0x380e386:
    0x380e386 | 49 8b cf                 | mov rcx, r15
    0x380e389 | e8 52 f6 f0 ff           | call 0x371d9e0
    0x380e38e | 90                       | nop
    0x380e38f | 48 8b 4e 08              | mov rcx, qword ptr [rsi + 0x8]
    0x380e393 | 48 85 c9                 | test rcx, rcx
    0x380e396 | 74 06                    | je 0x380e39e
    0x380e398 | e8 a3 cb ec fc           | call 0x6daf40
    0x380e39d | 90                       | nop
    L_0x380e39e:
    0x380e39e | 49 8b 4c 24 08           | mov rcx, qword ptr [r12 + 0x8]
    0x380e3a3 | 48 85 c9                 | test rcx, rcx
    0x380e3a6 | 74 06                    | je 0x380e3ae
    0x380e3a8 | e8 93 cb ec fc           | call 0x6daf40
    0x380e3ad | 90                       | nop
    L_0x380e3ae:
    0x380e3ae | 48 8b 4f 08              | mov rcx, qword ptr [rdi + 0x8]
    0x380e3b2 | 48 85 c9                 | test rcx, rcx
    0x380e3b5 | 74 1a                    | je 0x380e3d1
    0x380e3b7 | f0 44 0f c1 71 0c        | lock xadd dword ptr [rcx + 0xc], r14d
    0x380e3bd | 41 83 fe 01              | cmp r14d, 0x1
    0x380e3c1 | 75 0e                    | jne 0x380e3d1
    0x380e3c3 | 48 8b 01                 | mov rax, qword ptr [rcx]
    0x380e3c6 | 48 8b 40 08              | mov rax, qword ptr [rax + 0x8]
    0x380e3ca | ff 15 70 b9 c2 02        | call qword ptr [rip + 0x2c2b970] ; __guard_dispatch_icall_fptr (0x6439d40)
    0x380e3d0 | 90                       | nop
    L_0x380e3d1:
    0x380e3d1 | 49 8b 4d 08              | mov rcx, qword ptr [r13 + 0x8]
    0x380e3d5 | 48 85 c9                 | test rcx, rcx
    0x380e3d8 | 74 06                    | je 0x380e3e0
    0x380e3da | e8 61 cb ec fc           | call 0x6daf40
    0x380e3df | 90                       | nop
    L_0x380e3e0:
    0x380e3e0 | 48 8b 4d c8              | mov rcx, qword ptr [rbp - 0x38]
    0x380e3e4 | 48 8b 49 08              | mov rcx, qword ptr [rcx + 0x8]
    0x380e3e8 | 48 85 c9                 | test rcx, rcx
    0x380e3eb | 74 05                    | je 0x380e3f2
    0x380e3ed | e8 4e cb ec fc           | call 0x6daf40
    L_0x380e3f2:
    0x380e3f2 | 48 8b 8d f0 05 00 00     | mov rcx, qword ptr [rbp + 0x5f0]
    0x380e3f9 | 48 33 cc                 | xor rcx, rsp
    0x380e3fc | e8 9f 64 5d 02           | call 0x5de48a0
    0x380e401 | 48 81 c4 08 07 00 00     | add rsp, 0x708
    0x380e408 | 41 5f                    | pop r15
    0x380e40a | 41 5e                    | pop r14
    0x380e40c | 41 5d                    | pop r13
    0x380e40e | 41 5c                    | pop r12
    0x380e410 | 5f                       | pop rdi
    0x380e411 | 5e                       | pop rsi
    0x380e412 | 5b                       | pop rbx
    0x380e413 | 5d                       | pop rbp
    0x380e414 | c3                       | ret
  
  === [Sub-Rotina Chamada: 0x374f270..0x374f368 via call @0x380e086 (rcx = this (Direct Engine Sub-Call))] ===
    struct RBX::DebugDisable {
      /* +0x0 */ uint8_t field_0x0;
      /* +0x4 */ int32_t field_0x4;
      /* +0x14 */ double  field_0x14;
      /* +0x78 */ void*   field_0x78;
      /* +0x80 */ void*   field_0x80;
      /* +0x88 */ int32_t field_0x88;
      /* +0x98 */ double  field_0x98;
      /* +0xa0 */ int32_t field_0xa0;
      /* +0xb0 */ int32_t field_0xb0;
      /* +0x240 */ void*   field_0x240;
    };
    
    // Flag defaults: DebugDisableVoxelAsyncReadMeshing = false
    auto RBX::DebugDisable::func_0x374f270(RBX::DebugDisable* this, int64_t param_2) {
      this->field_0x0 = param_2->field_0x0;
      this->field_0x4 = param_2->field_0x4;
      this->field_0x14 = param_2->field_0x14;
      call_0x83b180(&this->field_0x20, &param_2->field_0x20);
      this->field_0x78 = 0;
      this->field_0x80 = 0;
      if (param_2->field_0x80 != 0) {
        param_2->field_0x80->field_0x8 = param_2->field_0x80->field_0x8 + 1;
      }
      this->field_0x78 = param_2->field_0x78;
      this->field_0x80 = param_2->field_0x80;
      this->field_0x88 = param_2->field_0x88;
      this->field_0x98 = param_2->field_0x98;
      this->field_0xa0 = param_2->field_0xa0;
      this->field_0xb0 = param_2->field_0xb0;
      call_0x5de50d4(&this->field_0xc0, &param_2->field_0xc0, 128, 3);
      this->field_0x240 = param_2->field_0x240;
      return this;
    }
  
  === [Instrucoes x86-64 da Sub-Rotina Chamada (0x374f270..0x374f368)] ===
    0x374f270 | 48 89 5c 24 10           | mov qword ptr [rsp + 0x10], rbx
    0x374f275 | 48 89 4c 24 08           | mov qword ptr [rsp + 0x8], rcx
    0x374f27a | 57                       | push rdi
    0x374f27b | 48 83 ec 30              | sub rsp, 0x30
    0x374f27f | 48 8b fa                 | mov rdi, rdx
    0x374f282 | 48 8b d9                 | mov rbx, rcx
    0x374f285 | 0f b6 02                 | movzx eax, byte ptr [rdx]
    0x374f288 | 88 01                    | mov byte ptr [rcx], al
    0x374f28a | 0f 10 42 04              | movups xmm0, xmmword ptr [rdx + 0x4]
    0x374f28e | 0f 11 41 04              | movups xmmword ptr [rcx + 0x4], xmm0
    0x374f292 | f2 0f 10 4a 14           | movsd xmm1, qword ptr [rdx + 0x14]
    0x374f297 | f2 0f 11 49 14           | movsd qword ptr [rcx + 0x14], xmm1
    0x374f29c | 48 83 c1 20              | add rcx, 0x20
    0x374f2a0 | 48 83 c2 20              | add rdx, 0x20
    0x374f2a4 | e8 d7 be 0e fd           | call 0x83b180
    0x374f2a9 | 90                       | nop
    0x374f2aa | 33 c0                    | xor eax, eax
    0x374f2ac | 48 89 43 78              | mov qword ptr [rbx + 0x78], rax
    0x374f2b0 | 48 89 83 80 00 00 00     | mov qword ptr [rbx + 0x80], rax
    0x374f2b7 | 48 8b 87 80 00 00 00     | mov rax, qword ptr [rdi + 0x80]
    0x374f2be | 48 85 c0                 | test rax, rax
    0x374f2c1 | 74 04                    | je 0x374f2c7
    0x374f2c3 | f0 ff 40 08              | lock inc dword ptr [rax + 0x8]
    L_0x374f2c7:
    0x374f2c7 | 48 8b 47 78              | mov rax, qword ptr [rdi + 0x78]
    0x374f2cb | 48 89 43 78              | mov qword ptr [rbx + 0x78], rax
    0x374f2cf | 48 8b 87 80 00 00 00     | mov rax, qword ptr [rdi + 0x80]
    0x374f2d6 | 48 89 83 80 00 00 00     | mov qword ptr [rbx + 0x80], rax
    0x374f2dd | 0f 10 87 88 00 00 00     | movups xmm0, xmmword ptr [rdi + 0x88]
    0x374f2e4 | 0f 11 83 88 00 00 00     | movups xmmword ptr [rbx + 0x88], xmm0
    0x374f2eb | f2 0f 10 8f 98 00 00 00  | movsd xmm1, qword ptr [rdi + 0x98]
    0x374f2f3 | f2 0f 11 8b 98 00 00 00  | movsd qword ptr [rbx + 0x98], xmm1
    0x374f2fb | 0f 10 87 a0 00 00 00     | movups xmm0, xmmword ptr [rdi + 0xa0]
    0x374f302 | 0f 11 83 a0 00 00 00     | movups xmmword ptr [rbx + 0xa0], xmm0
    0x374f309 | 0f 10 8f b0 00 00 00     | movups xmm1, xmmword ptr [rdi + 0xb0]
    0x374f310 | 0f 11 8b b0 00 00 00     | movups xmmword ptr [rbx + 0xb0], xmm1
    0x374f317 | 48 8d 97 c0 00 00 00     | lea rdx, [rdi + 0xc0]
    0x374f31e | 48 8d 8b c0 00 00 00     | lea rcx, [rbx + 0xc0]
    0x374f325 | 48 8d 05 e4 7d ff ff     | lea rax, [rip - 0x821c]
    0x374f32c | 48 89 44 24 28           | mov qword ptr [rsp + 0x28], rax
    0x374f331 | 48 8d 05 38 00 00 00     | lea rax, [rip + 0x38]
    0x374f338 | 48 89 44 24 20           | mov qword ptr [rsp + 0x20], rax
    0x374f33d | 41 b9 03 00 00 00        | mov r9d, 0x3
    0x374f343 | 45 8d 41 7d              | lea r8d, [r9 + 0x7d]
    0x374f347 | e8 88 5d 69 02           | call 0x5de50d4
    0x374f34c | 48 8b 87 40 02 00 00     | mov rax, qword ptr [rdi + 0x240]
    0x374f353 | 48 89 83 40 02 00 00     | mov qword ptr [rbx + 0x240], rax
    0x374f35a | 48 8b c3                 | mov rax, rbx
    0x374f35d | 48 8b 5c 24 48           | mov rbx, qword ptr [rsp + 0x48]
    0x374f362 | 48 83 c4 30              | add rsp, 0x30
    0x374f366 | 5f                       | pop rdi
    0x374f367 | c3                       | ret

[Bytecode Hex]
  0x380e000: 54 | 24 48 | 48 89 10 | 48 8b 44 24 48
  0x380e00b: 48 85 c0 | 74 07 | 48 c7 00 00 00 00 00 | 48 c7 44 24 50 00 00 00 00
  0x380e020: e9 61 03 00 00 | 49 8b 87 c0 00 00 00 | 80 78 15 00 | 74 1f
  0x380e032: 80 3d af d3 90 04 00 | 75 16 | 4c 8b cb | 4d 8b c5
  0x380e041: 49 8b d4 | 49 8b cf | e8 54 76 ff ff | e9 dc 00 00 00
  0x380e051: 49 8b d7 | 48 8d 4d 40 | e8 03 6c ff ff | 90
  0x380e05e: 80 bd 88 02 00 00 00 | 0f 84 86 00 00 00 | 49 8b d7 | 48 8d 8d a0 02 00 00
  0x380e075: e8 66 0f f4 ff | 90 | 48 8d 55 40 | 48 8d 8d a0 03 00 00
  0x380e086: e8 e5 11 f4 ff | 90 | 48 8d 95 a0 02 00 00 | 49 8b 4d 00
  0x380e097: e8 94 45 00 00 | 90 | 4c 8d 0d 6c 90 f3 ff | ba 80 00 00 00
  0x380e0a9: 44 8d 42 83 | 48 8d 8d 60 04 00 00 | e8 b7 68 5d 02 | 48 8b 8d 20 04 00 00
  0x380e0c0: 48 85 c9 | 74 05 | e8 76 ce ec fc | 48 8d 85 e0 03 00 00
  0x380e0d1: 48 8b 8d d0 03 00 00 | 48 3b c8 | 74 06 | e8 de 79 14 01
  0x380e0e2: 90 | 48 8d 8d a0 02 00 00 | e8 f1 f8 f0 ff | eb 27
  0x380e0f1: f2 41 0f 10 07 | f2 0f 11 45 00 | 41 8b 47 08 | 89 45 08
  0x380e102: 41 0f b6 47 0c | 89 45 0c | 48 8d 55 00 | 49 8b 0c 24
  0x380e112: e8 c9 45 00 00 | 90 | 80 bd 88 02 00 00 00 | 74 09
  0x380e121: 48 8d 4d 40 | e8 f6 57 00 00 | f0 ff 0b | 48 83 7c 24 68 ff
  0x380e133: 0f 84 26 02 00 00 | 48 8b 45 a8 | 33 f6 | 48 85 c0
  0x380e142: 74 45 | 8b d6 | 48 83 7d b0 01 | 0f 94 c2
  0x380e14e: 48 83 c2 02 | 48 c1 e2 30 | 48 b9 ff ff ff ff ff ff 00 00 | 48 23 c1
  0x380e163: 48 0b d0 | 48 89 75 e8 | 48 8d 45 e8 | 48 89 44 24 28
  0x380e173: 48 89 74 24 20 | 45 33 c9 | 45 33 c0 | b1 21
  0x380e180: e8 5b 61 19 ff | 48 89 75 b0 | 80 3d 46 63 c9 04 00 | 0f 84 eb 00 00 00
  0x380e196: 80 3d 83 5d 8f 04 00 | 0f 84 de 00 00 00 | e8 f8 1c 17 01 | 48 8b 08
  0x380e1ab: 48 85 c9 | 75 04 | 48 8d 48 08 | 8b 11
  0x380e1b6: 44 8b 41 04 | 4c 8b 49 08 | 4c 8b 59 10 | 8b 4d 98
  0x380e1c5: 85 c9 | 74 45 | 48 8b 7d 88 | 4c 3b cf
  0x380e1d0: 72 3c | 48 8b 5d 90 | 4c 3b db | 72 33
  0x380e1db: 3b d1 | 72 2f | 44 8b 55 9c | 45 3b c2
  0x380e1e6: 72 26 | 49 8b c1 | 48 2b c7 | 48 01 44 24 70
  0x380e1f3: 49 8b c3 | 48 2b c3 | 48 01 44 24 78 | 8b c2
  0x380e200: 2b c1 | 01 45 80 | 41 8b c0 | 41 2b c2
  0x380e20b: 01 45 84 | 48 8b 44 24 48 | 48 85 c0 | 74 0f
  0x380e218: 4c 89 48 48 | 4c 89 58 50 | 89 50 58 | 44 89 40 5c
  0x380e227: 48 8b 55 80 | 81 e2 ff ff ff 00 | 48 c1 e2 18 | 8b 45 84
  0x380e238: 25 ff ff ff 00 | 48 0b d0 | 48 8b 4c 24 70 | 48 c1 e1 20
  0x380e249: 8b 44 24 78 | 48 0b c8 | 48 89 4d f8 | 48 85 d2
  0x380e257: 75 05 | 48 85 c9 | 74 23 | 48 89 75 f0
  0x380e262: 48 8d 45 f0 | 48 89 44 24 28 | 48 89 74 24 20 | 41 b9 08 00 00 00
  0x380e276: 4c 8d 45 f8 | b1 14 | e8 5f 60 19 ff | 48 8b 74 24 50
  0x380e286: 48 83 7c 24 68 ff | 0f 84 98 00 00 00 | e8 29 39 19 ff | 48 8b 18
  0x380e29a: 48 85 db | 0f 84 87 00 00 00 | 48 8b ce | 48 c1 e9 0e
  0x380e2aa: 0f 31 | 48 c1 e2 20 | 48 0b c2 | 48 8b f8
  0x380e2b6: 48 2b 3d 73 c3 4c 05 | 48 8b 05 84 f3 95 04 | 48 85 88 b8 00 00 00 | 74 4c
  0x380e2cd: 80 bb 65 05 00 00 00 | 74 54 | 48 8b 80 a0 d5 26 00 | 48 85 c0
  0x380e2e0: 75 07 | b8 ff ff ff ff | eb 0a | 48 8b 4b 30
  0x380e2ed: ff 15 4d ba c2 02 | 8b d0 | 4c 8b 0d 1c b8 c6 04 | 45 33 c0
  0x380e2ff: 48 8b ce | e8 f9 55 19 ff | 8b 4b 44 | 4c 8b 0d 07 b8 c6 04
  0x380e311: 41 b8 04 00 00 00 | eb 09 | 4c 8b cb | 45 33 c0
  0x380e31f: 48 8b ce | 48 8b d7 | e8 d6 55 19 ff | 48 8b 44 24 50
  0x380e32f: 48 c1 e8 0e | 48 23 05 be b2 e1 04 | 48 85 05 37 b3 e1 04 | 74 12
  0x380e343: 48 8b 05 1e ec cc 04 | 48 85 c0 | 74 06 | ff 15 eb b9 c2 02
  0x380e355: 48 8b 7c 24 30 | 48 8b 74 24 38 | e8 6c 60 11 ff | 48 8b 4c 24 48
  0x380e369: 48 89 08 | 48 8b 44 24 48 | 48 85 c0 | 74 07
  0x380e376: 48 c7 00 00 00 00 00 | 48 c7 44 24 50 00 00 00 00 | 49 8b cf | e8 52 f6 f0 ff
  0x380e38e: 90 | 48 8b 4e 08 | 48 85 c9 | 74 06
  0x380e398: e8 a3 cb ec fc | 90 | 49 8b 4c 24 08 | 48 85 c9
  0x380e3a6: 74 06 | e8 93 cb ec fc | 90 | 48 8b 4f 08
  0x380e3b2: 48 85 c9 | 74 1a | f0 44 0f c1 71 0c | 41 83 fe 01
  0x380e3c1: 75 0e | 48 8b 01 | 48 8b 40 08 | ff 15 70 b9 c2 02
  0x380e3d0: 90 | 49 8b 4d 08 | 48 85 c9 | 74 06
  0x380e3da: e8 61 cb ec fc | 90 | 48 8b 4d c8 | 48 8b 49 08
  0x380e3e8: 48 85 c9 | 74 05 | e8 4e cb ec fc | 48 8b 8d f0 05 00 00
  0x380e3f9: 48 33 cc | e8 9f 64 5d 02 | 48 81 c4 08 07 00 00 | 41 5f
  0x380e40a: 41 5e | 41 5d | 41 5c | 5f
  0x380e411: 5e | 5b | 5d | c3

  [Child Bytecode Hex 0x374f270..0x374f368]
  0x374f270: 48 89 5c 24 10 | 48 89 4c 24 08 | 57 | 48 83 ec 30
  0x374f27f: 48 8b fa | 48 8b d9 | 0f b6 02 | 88 01
  0x374f28a: 0f 10 42 04 | 0f 11 41 04 | f2 0f 10 4a 14 | f2 0f 11 49 14
  0x374f29c: 48 83 c1 20 | 48 83 c2 20 | e8 d7 be 0e fd | 90
  0x374f2aa: 33 c0 | 48 89 43 78 | 48 89 83 80 00 00 00 | 48 8b 87 80 00 00 00
  0x374f2be: 48 85 c0 | 74 04 | f0 ff 40 08 | 48 8b 47 78
  0x374f2cb: 48 89 43 78 | 48 8b 87 80 00 00 00 | 48 89 83 80 00 00 00 | 0f 10 87 88 00 00 00
  0x374f2e4: 0f 11 83 88 00 00 00 | f2 0f 10 8f 98 00 00 00 | f2 0f 11 8b 98 00 00 00 | 0f 10 87 a0 00 00 00
  0x374f302: 0f 11 83 a0 00 00 00 | 0f 10 8f b0 00 00 00 | 0f 11 8b b0 00 00 00 | 48 8d 97 c0 00 00 00
  0x374f31e: 48 8d 8b c0 00 00 00 | 48 8d 05 e4 7d ff ff | 48 89 44 24 28 | 48 8d 05 38 00 00 00
  0x374f338: 48 89 44 24 20 | 41 b9 03 00 00 00 | 45 8d 41 7d | e8 88 5d 69 02
  0x374f34c: 48 8b 87 40 02 00 00 | 48 89 83 40 02 00 00 | 48 8b c3 | 48 8b 5c 24 48
  0x374f362: 48 83 c4 30 | 5f | c3

[Strings .rdata na função]
  (Nenhuma string literal direta neste bloco)

[Co-Flags na mesma função]
  * DFFlagMicroProfilerMemoryScope = true (default)
  * FIntSSAOMipLevels = 4 (default) [vizinha em .data]
  * FFlagRenderSSAOFrameIndexWrapFix = true (default) [vizinha em .data]
  * FIntViewportFrameMaxSize = 1024 (default) [vizinha em .data]
  * FFlagSkipVJMVoxelDataCopyWithoutVT = true (default) [vizinha em .data]
  * DFFlagDebugDisableSmoothClusterCullStaleUpdates = false (default) [vizinha em .data]
  * FFlagSmoothClusterMeshTaskHeuristic = false (default) [vizinha em .data]
  * FFlagVJMAsyncMeshUpload = true (default) [vizinha em .data]
  * FFlagSmoothClusterDisableAsyncUpload = false (default) [vizinha em .data]
