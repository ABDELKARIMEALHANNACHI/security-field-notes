# Prevention, Detection, and Recovery

## Prevention

- Remove unnecessary direct internet exposure from management interfaces.
- Restrict administration to a protected network or secure VPN.
- Replace default credentials and review shared accounts.
- Apply vendor-recommended firmware and security settings.
- Track supported and end-of-life devices.
- Enforce least privilege for operators and external technicians.
- Segment OT equipment from general business networks where feasible.

## Detection

Monitor:

- Unexpected temperature and defrost-setting changes.
- Administrative access outside approved windows.
- Unrecognized remote-access sources.
- Configuration changes that do not match the approved baseline.
- Loss of expected telemetry or unusual controller behavior.
- Changes to firewall rules or remote-management settings.

## Response and recovery

1. Coordinate with operations and qualified refrigeration personnel.
2. Reduce exposure safely and preserve relevant evidence.
3. Determine whether the equipment is compromised.
4. Restore trusted configuration and factory-reset when required by the recovery plan.
5. Reconfigure protected access and apply vendor-recommended updates.
6. Verify safe physical operation before returning the system to service.
7. Review how the incident occurred and improve controls.

## Important limitation

A factory reset alone does not fix an underlying vulnerability. If an unsupported or vulnerable device remains exposed, it may be compromised again.
