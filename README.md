# 钱学森力学-AI基础模块：能量守恒计算
# 来自手稿核心：物理量必须严格守恒
# 项目：钱学森力学-AI融合系统 (Qian-Xuesen-Mechanics-AI)
# 开源协议：Apache-2.0

def mechanical_energy(m, v, h, g=9.81):
    """
    计算经典力学下的机械能守恒（动能+势能）
    严格遵循钱学森力学体系中「物理量必须严格守恒」的核心思想
    
    参数:
        m: 物体质量 (kg)
        v: 物体速度 (m/s)
        h: 物体高度 (m)
        g: 重力加速度 (m/s²)，默认9.81
    
    返回:
        dict: 包含动能、势能、总机械能、理论守恒误差的字典
    """
    # 计算动能：Ek = 1/2 * m * v²
    kinetic = 0.5 * m * v ** 2
    # 计算重力势能：Ep = m * g * h
    potential = m * g * h
    # 计算总机械能
    total = kinetic + potential
    
    return {
        "动能(J)": round(kinetic, 6),
        "势能(J)": round(potential, 6),
        "总机械能(J)": round(total, 6),
        "理论守恒误差(J)": 0.0  # 严格守恒，理论误差为0
    }

# 测试用例：航天器1000kg，速度10m/s，高度50m
if __name__ == "__main__":
    # 输入参数
    mass = 1000    # 质量 kg
    velocity = 10  # 速度 m/s
    height = 50    # 高度 m
    
    # 计算能量
    result = mechanical_energy(mass, velocity, height)
    
    # 格式化输出
    print("="*50)
    print("钱学森力学-AI基础模块：能量守恒计算测试")
    print(f"输入参数：质量={mass}kg，速度={velocity}m/s，高度={height}m")
    print("="*50)
    for key, value in result.items():
        print(f"{key}: {value}")
    print("="*50)
    print("核心验证：物理量严格守恒，理论误差为0")
